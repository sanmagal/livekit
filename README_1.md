# LiveKit Deploy para Coolify

Deploy do LiveKit Server usando Docker Compose no Coolify.

## 🚀 Deploy no Coolify

### 1. Conectar GitHub ao Coolify
- No Coolify, vá em **Sources** e conecte sua conta GitHub
- Autorize o acesso ao repositório

### 2. Criar Nova Aplicação
1. Clique em **+ New Resource** → **Application**
2. Escolha **Git Repository**
3. Selecione este repositório
4. Branch: `main` (ou o branch que você usar)

### 3. Configurar a Aplicação
- **Build Pack**: Docker Compose
- **Port**: `7880` (porta principal HTTP/WS)
- **Domain**: `livekit.itfp.eu`

### 4. Portas Adicionais (IMPORTANTE!)
No servidor onde o Coolify roda, abra as portas no firewall:

```bash
# UFW (Ubuntu/Debian)
sudo ufw allow 7881/tcp
sudo ufw allow 7881/udp

# Firewalld (CentOS/RHEL)
sudo firewall-cmd --permanent --add-port=7881/tcp
sudo firewall-cmd --permanent --add-port=7881/udp
sudo firewall-cmd --reload
