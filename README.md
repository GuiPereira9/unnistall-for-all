# unnistall-for-all
# 🗑️ Linux Uninstaller Toy

O **Linux Uninstaller Toy** é um script Bash simples, interativo e visual que atua como um desinstalador universal para distribuições Linux. Inspirado na leveza e diversão dos "Linux toys" de terminal, ele utiliza o `zenity` para fornecer uma interface gráfica amigável, unificando a remoção de aplicativos de diversas origens em um único lugar.

## ✨ Funcionalidades

O script é capaz de detectar e desinstalar aplicativos das seguintes fontes:
- **📦 Pacotes Nativos:** Suporte automático para `apt` (Debian/Ubuntu), `dnf` (Fedora/RHEL) e `pacman` (Arch Linux).
- **📦 Sandbox:** Suporte nativo para remoção de **Flatpaks** e **Snaps**.
- **🚀 AppImages:** Detecta arquivos `.AppImage` integrados ao menu do sistema (`~/.local/share/applications`) e remove tanto o atalho quanto o arquivo físico.
- **⚙️ Instaladores Customizados em `/opt/`:** Varre a pasta `/opt/` em busca de scripts de desinstalação (ex: `uninstall.sh`, `maintenance-tool`) deixados por programas como DaVinci Resolve, XAMPP, entre outros.
- **🖥️ VMware Bundles:** Detecta e executa automaticamente a desinstalação de produtos VMware (Workstation/Player) instalados via arquivo `.bundle`.

### 🛡️ Proteção do Sistema (Anti-Quebra)
O script possui um filtro de segurança integrado. Pacotes essenciais para o boot do sistema (como `systemd`, `grub`, `linux-image`) ou para a interface gráfica (como `xorg`, `gnome-shell`, `plasma-desktop`) são:
1. Destacados em **vermelho** na lista.
2. Sinalizados com a tag de status **CRÍTICO**.
3. Protegidos por uma **dupla barreira de confirmação** para evitar que o usuário quebre o sistema acidentalmente.

## 🛠️ Pré-requisitos

Para que o script funcione corretamente, você precisará ter instalado na sua distribuição:
- `zenity` (Responsável por gerar a interface gráfica).
- `pkexec` (Polkit - Responsável por pedir a senha de administrador graficamente).

*Em muitas distribuições com interface gráfica (GNOME, KDE, XFCE), esses pacotes já vêm instalados por padrão.*

## 🚀 Como usar

1. Clone este repositório:
   ```bash
   git clone [https://github.com/SEU_USUARIO/linux-uninstaller-toy.git](https://github.com/SEU_USUARIO/linux-uninstaller-toy.git)
   cd linux-uninstaller-toy
