# Flutter Docker

amd64 Docker image for Flutter, built and pushed to **GitHub Container Registry** (ghcr.io).

## Usage

### Local build

```bash
docker build -t flutter:3.44.1 \
    --build-arg FLUTTER_VERSION=3.44.1 \
    stable
```

```bash
docker run --rm flutter:3.44.1 flutter --version
```

### Build & Push (GitHub Actions)

Manually trigger via **Actions → Build & Push Flutter Docker Image → Run Workflow**, specifying the Flutter version.

Tags pushed to `ghcr.io`:
- `ghcr.io/{repo}:latest`
- `ghcr.io/{repo}:{version}`

## Structure

```
stable/Dockerfile                     # Flutter image (debian:stable-slim)
.github/workflows/build_and_push.yaml # GitHub Actions workflow
```
