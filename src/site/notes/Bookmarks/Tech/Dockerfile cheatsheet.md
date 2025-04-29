---
{"dg-publish":true,"permalink":"/bookmarks/tech/dockerfile-cheatsheet/","tags":["coding","dev","linux","tools"]}
---


# [Dockerfile Best Practices: How to Create Efficient Containers](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o)

```table-of-contents

```

## [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o) Introduction

In the era of microservices and cloud computing, Docker has become an indispensable tool for application development and deployment. Containerization allows developers to package applications and their dependencies into a single, portable unit, ensuring predictability, scalability, and rapid deployment. However, the efficiency of your containers largely depends on how optimally your Dockerfile is written.

In this article, we'll explore best practices for creating Dockerfiles that help you build lightweight, fast, and secure containers.

## [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8ofile-basics) Dockerfile Basics

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#what-is-a-dockerfile) What Is a Dockerfile?

A Dockerfile is a text document containing a set of instructions to assemble a Docker image. Each instruction performs a specific action, such as installing packages, copying files, or defining startup commands. Proper use of Dockerfile instructions is crucial for building efficient containers.

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#key-dockerfile-instructions) Key Dockerfile Instructions

- **FROM**: Sets the base image for your new image.
- **RUN**: Executes a command in a new layer on top of the current image and commits the result.
- **CMD**: Specifies the default command to run when a container is started.
- **COPY**: Copies files and directories from the build context into the container filesystem.
- **ADD**: Similar to COPY but with additional features like extracting archives.
- **ENV**: Sets environment variables.
- **EXPOSE**: Informs Docker which ports the container listens on at runtime.
- **ENTRYPOINT**: Configures a container to run as an executable.
- **VOLUME**: Creates a mount point for external storage volumes.
- **WORKDIR**: Sets the working directory for subsequent instructions.

## [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o) Best Practices for Writing Dockerfiles

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#use-minimal-base-images) Use Minimal Base Images

The base image serves as the foundation for your Docker image. Choosing a lightweight base image can significantly reduce the final image size and minimize the attack surface.

- **Alpine Linux**: A popular minimal image around 5 MB in size.

```
  FROM alpine:latest

```

Enter fullscreen modeExit fullscreen mode

_Pros_: Small size, security, fast downloads.

_Cons_: May require additional configuration; some packages might be missing or behave differently due to using musl instead of glibc.

- **Scratch**: An empty image ideal for languages that can compile static binaries (Go, Rust).

```
  FROM scratch
  COPY myapp /myapp
  CMD ["/myapp"]

```

Enter fullscreen modeExit fullscreen mode

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#reduce-layers) Reduce Layers

Each `RUN`, `COPY`, and `ADD` instruction adds a new layer to your image. Combining commands helps reduce the number of layers and the overall image size.

**Inefficient:**

```
RUN apt-get update
RUN apt-get install-y python
RUN apt-get install-y pip

```

Enter fullscreen modeExit fullscreen mode

**Efficient:**

```
RUN apt-get update && apt-get install-y\
    python \
    pip \
&&rm-rf /var/lib/apt/lists/*
```

Enter fullscreen modeExit fullscreen mode

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#optimize-layer-caching) Optimize Layer Caching

Docker uses layer caching to speed up builds. The order of instructions affects caching efficiency.

- **Copy Dependency Files First**: Copy files that change less frequently (like `package.json` or `requirements.txt`) before copying the rest of the source code.

```
  COPY package.json .
  RUN npm install
  COPY . .

```

Enter fullscreen modeExit fullscreen mode

- **Minimize Changes in Early Layers**: Changes in early layers invalidate the cache for all subsequent layers.

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#install-dependencies-wisely) Install Dependencies Wisely

Remove temporary files and caches after installing packages to reduce image size.

```
RUN pip install--no-cache-dir-r requirements.txt

```

Enter fullscreen modeExit fullscreen mode

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#manage-secrets-carefully) Manage Secrets Carefully

Never include sensitive data (passwords, API keys) in your Dockerfile.

- **Use Environment Variables**: Pass secrets at runtime using environment variables.
- **Leverage Docker Secrets**: Use Docker Swarm or Kubernetes mechanisms for managing secrets.

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#optimize-image-size) Optimize Image Size

- **Delete Unnecessary Files**: Clean up caches, logs, and temporary files after installation.

```
  RUN apt-get clean && rm -rf /var/lib/apt/lists/*

```

Enter fullscreen modeExit fullscreen mode

- **Minimize Installed Packages**: Install only the packages you need.

```
  RUN apt-get install -y --no-install-recommends package

```

Enter fullscreen modeExit fullscreen mode

- **Use Optimization Tools**: Tools like **Docker Slim** can automatically optimize your images.

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#utilize-dockerignore) Utilize .dockerignore

A `.dockerignore` file lets you exclude files and directories from the build context, reducing the amount of data sent to the Docker daemon and protecting sensitive information.

**Example .dockerignore:**

```
.git
node_modules
Dockerfile
.dockerignore

```

Enter fullscreen modeExit fullscreen mode

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#employ-multistage-builds) Employ Multi-Stage Builds

Multi-stage builds allow you to use intermediate images and copy only the necessary artifacts into the final image.

**Example for a Go Application:**

```
# Build StageFROMgolang:1.16-alpineASbuilderWORKDIR /appCOPY . .RUN go build -o myapp

# Final ImageFROM alpine:latestWORKDIR /appCOPY --from=builder /app/myapp .CMD ["./myapp"]
```

Enter fullscreen modeExit fullscreen mode

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#run-as-nonroot-user) Run as Non-Root User

For enhanced security, avoid running applications as the root user.

```
RUN adduser -D appuser
USER appuser
```

Enter fullscreen modeExit fullscreen mode

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#scan-for-vulnerabilities) Scan for Vulnerabilities

- **Use Scanning Tools**: Tools like **Trivy**, **Anchore**, or **Clair** can help identify known vulnerabilities.
- **Regularly Update Images**: Keep your base images and dependencies up to date.

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#logging-and-monitoring) Logging and Monitoring

- **Direct Logs to STDOUT/STDERR**: This allows for easier log collection and analysis.
- **Integrate with Monitoring Systems**: Use tools like Prometheus or the ELK Stack to monitor container health.

## [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o) Examples and Recommendations

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#optimized-dockerfile-example-for-a-nodejs-application) Optimized Dockerfile Example for a Node.js Application

```
# Use the official Node.js image based on Alpine LinuxFROM node:14-alpine# Set the working directoryWORKDIR /app# Copy package files and install dependenciesCOPY package*.json ./RUN npm ci --only=production

# Copy the rest of the application codeCOPY . .# Create a non-root user and switch to itRUN addgroup appgroup && adduser -S appuser -G appgroup
USER appuser# Expose the application portEXPOSE 3000# Define the command to run the appCMD ["node", "app.js"]
```

Enter fullscreen modeExit fullscreen mode

### [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o#additional-recommendations) Additional Recommendations

- **Pin Versions**: Use specific versions of base images and packages to ensure build reproducibility.

```
  FROM node:14.17.0-alpine

```

Enter fullscreen modeExit fullscreen mode

- **Stay Updated**: Regularly update dependencies and base images to include security patches.
- **Use Metadata**: Add `LABEL` instructions to provide image metadata.

```
  LABEL maintainer="yourname@example.com"

```

Enter fullscreen modeExit fullscreen mode

- **Set Proper Permissions**: Ensure files and directories have appropriate permissions.
- **Avoid Using Root**: Always switch to a non-root user for running applications.

## [](https://dev.to/idsulik/dockerfile-best-practices-how-to-create-efficient-containers-4p8o) Conclusion

Creating efficient Docker images is both an art and a science. By following best practices when writing your Dockerfile, you can significantly improve the performance, security, and manageability of your containers. Continuously update your knowledge and stay informed about new tools and methodologies in the containerization ecosystem. Remember, optimization is an ongoing process, and there's always room for improvement.
