# 🐳 Portainer Deployment Repository

이 저장소는 **Docker Compose** 또는 **Docker Swarm**을 사용하여 **Portainer**를 배포하기 위한 설정 파일들을 제공합니다.

## 🛠️ 사전 준비

**Docker Swarm** 클러스터에 **Synology** 노드가 포함되어 있다면 해당 노드에는 `os=synology` 라벨을 추가해야 합니다.

## 🚀 배포 방법

### Docker Swarm

매니저 노드에서 다음 명령어를 실행합니다.

```bash
curl -L https://raw.githubusercontent.com/E4-Docker/project-portainer/refs/heads/main/docker-stack.yml | docker stack deploy -c - portainer
```