# Гайд на ноду Succinct

![header-1](https://github.com/user-attachments/assets/c05850d5-2fd3-4b11-9fc9-8f7ce35dbb2b)


**Обновляем пакеты на сервере:**

``sudo apt update && sudo apt upgrade -y``

```sudo apt install cmake pkg-config libssl-dev build-essential -y```

**Устанавливаем Rust и Cargo**

```curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh```

```source $HOME/.cargo/env```

**Скачиваем докер**

```curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg```

```echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | ```

```sudo tee /etc/apt/sources.list.d/docker.list > /dev/null```

```sudo apt-get update >/dev/null 2>&1```

```sudo apt-get install -y docker-ce docker-ce-cli containerd.io >/dev/null 2>&1```

```sudo docker run hello-world >/dev/null 2>&1```


**Проверяем версию докера**

```docker --version```

**Приступим к установке ноды**

```curl -L https://sp1.succinct.xyz | bash```

```source ~/.bashrc```

```sp1up```
<img width="1130" alt="Снимок экрана 2024-10-24 в 18 32 53" src="https://github.com/user-attachments/assets/e00dbf16-0611-4770-8c63-ab6a74529c76">


**Проверяем, установился ли succinct**

```cargo +succinct --version```

**Создаем новый проект fibonacci с использованием cargo и переходим в директорию fibonacci/script**

```cargo prove new fibonacci --bare```

```cd fibonacci/script```

**Запускаем ноду** (придется подождать 10-15 минут)

```RUST_LOG=info cargo run --release -- --execute```

<img width="970" alt="Снимок экрана 2024-10-24 в 18 51 32" src="https://github.com/user-attachments/assets/c6a36e64-5993-4b91-a07a-2426f9a54f51">


```RUST_LOG=info cargo run --release -- --prove```
