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

## ⚙️ Portainer 환경 설정

배포 완료 후 **Portainer** 환경 설정이 필요합니다.

1. 왼쪽 사이드 바 메뉴에서 **Administration** > **Environment-related** > **Environments** 선택 후 `Add environment` 버튼 클릭
2. **Docker Swarm** 선택 후 `Start wizard` 버튼 클릭
3. **Agent** 선택 후 다음 정보 입력
    - **Name**: `agent` (자유롭게 입력)
    - **Environment URL**: `tasks.portainer_agent:9001`
4. `Connect` 버튼 클릭