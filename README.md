# secured-edge-ai-project
Secured-Edge-AI-Project enables robust and privacy-preserving AI processing at the edge, minimizing data exposure and latency. It integrates advanced encryption and lightweight models to ensure secure, real-time decision-making on local devices.


# 🐳 Docker Guide for Secured Edge AI Project

This section explains how to use Docker to create a clean, reproducible, and isolated environment for running and testing machine learning inference in this project.

---

## 📁 Docker Directory Structure

This Docker workflow is contained within the `docker_testing/` directory. Your entire project is mounted inside the container so that changes persist.

```bash
secured-edge-ai-project/
├── docker_testing/
│   ├── Dockerfile
│   ├── requirements.txt
│   └── test_tflite.py  # Example script (optional)
├── colab_notebooks/
├── esp32_firmware/
├── datasets/
├── results/


## 🚀 1. Build the Docker Image (Only Once)
cd docker_testing
docker build -t edge-ai-env .

## 🏃 2. Run the Docker Container
docker run -it --rm -v $(pwd):/app -w /app edge-ai-env

-it: Interactive shell
--rm: Deletes the container after exit (clean)
-v: Mounts your project directory into the container
-w: Sets working directory inside the container
edge-ai-env: Name of the image

## 🧪 3. Run Your Code Inside Docker
cd docker_testing
python test_tflite.py


## ❌ 4. Exit Docker
exit

## 🧹 5. Cleanup Docker (Optional at the end)
docker rmi edge-ai-env

