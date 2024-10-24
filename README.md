
sudo apt update && sudo apt upgrade -y
sudo apt install cmake pkg-config libssl-dev build-essential -y
Rust and Cargo Installation

curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

source $HOME/.cargo/env
 # Скачиваем докер 
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update >/dev/null 2>&1
sudo apt-get install -y docker-ce docker-ce-cli containerd.io >/dev/null 2>&1
sudo docker run hello-world >/dev/null 2>&1

# Проверяем версию докера
docker --version

# Приступим к установке ноды

curl -L https://sp1.succinct.xyz | bash
source ~/.bashrc
sp1up

# Проверяем, установился ли succinct
cargo +succinct --version

# команда последовательно создаёт новый проект fibonacci с использованием cargo и затем переходит в директорию fibonacci/script.
cargo prove new fibonacci
cd fibonacci/script

# Запускаем ноду 
RUST_LOG=info cargo run --release -- --execute
RUST_LOG=info cargo run --release -- --prove
