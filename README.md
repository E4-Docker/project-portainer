# 🐳 Portainer Deployment Repository

이 저장소는 **Docker Compose** 또는 **Docker Swarm**을 사용하여 **Portainer**를 배포하기 위한 설정 파일들을 제공합니다.

## 🛠️ 사전 준비

### Linux

**Docker Swarm** 클러스터에 **Synology** 노드가 포함되어 있다면 해당 노드에는 `os=synology` 라벨을 추가해야 합니다.

## 🚀 배포 방법

### 1. Linux

#### Docker Swarm

```bash
curl -L https://raw.githubusercontent.com/E4-Docker/project-portainer/refs/heads/main/docker-stack.yml | docker stack deploy -c - portainer
```

### 2. Windows

#### Docker Compose

```powershell
Invoke-RestMethod -Uri "https://raw.githubusercontent.com/E4-Docker/project-portainer/refs/heads/main/windows/docker-compose.yml" | docker-compose -f - -p portainer up -d
```

#### Docer Swarm

```powershell
Invoke-RestMethod -Uri "https://raw.githubusercontent.com/E4-Docker/project-portainer/refs/heads/main/windows/docker-stack.yml" | docker stack deploy -c - portainer
```

## 🧹 정리 방법

### Linux & Windows

#### Docker Compose
```powershell
docker compose -p portainer down
```

#### Docker Swarm

```powershell
docker stack rm portainer
```

## ⚙️ Portainer 환경 설정

### Linux

1. 왼쪽 사이드 바 메뉴에서 **Administration** > **Environment-related** > **Environments** 선택 후 `Add environment` 버튼 클릭
2. **Docker Swarm** 선택 후 `Start wizard` 버튼 클릭
3. **Agent** 선택 후 다음 정보 입력
    - **Name**: `agent` (자유롭게 입력)
    - **Environment URL**: `tasks.portainer_agent:9001`
4. `Connect` 버튼 클릭