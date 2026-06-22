# Docker Hardened 🐳

Security-hardened Docker images with distroless base and supply chain security.

## Features

- **Distroless base**: No shell, minimal attack surface
- **Multi-stage builds**: Small final image size
- **Trivy scanning**: CVE detection in CI
- **Sigstore signing**: Image provenance
- **Non-root user**: UID 65534

## Size Comparison

| Image | Standard | Hardened |
|-------|----------|----------|
| Python | 912MB | 85MB |
| Node.js | 1.1GB | 120MB |
| Go | 800MB | 15MB |

## Quick Start

```dockerfile
FROM gcr.io/distroless/python3-debian12
COPY --from=builder /app /app
USER nonroot
ENTRYPOINT ["/app/main"]
```

## License

Apache 2.0