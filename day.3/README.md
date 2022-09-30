# Configuração do AWS CLI

### Link para instalação
<https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html>

## Linux
---

```sh
$ curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install

$ aws --version
$ aws-cli/2.4.27 Python/3.8.8 Linux/5.10.16.3-microsoft-standard-WSL2 exe/x86_64.ubuntu.20 prompt/off
```

## MacOS

### <https://formulae.brew.sh/formula/awscli>

---

```sh
brew install awscli
```

## Windows

---

### Baixe o instalador MSI para Windows PowerShell
<https://awscli.amazonaws.com/AWSCLIV2.msi>

---

## Uma outra alternativa é instalar através do msiexec executando o comando abaixo

```sh
C:\> msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi

# To confirm the installation, open the Start menu, search for cmd to open a command prompt window, and at the command prompt use the aws --version command.
C:\> aws --version
aws-cli/2.4.5 Python/3.8.8 Windows/10 exe/AMD64 prompt/off
```

### Após instalação configure suas credenciais de acesso

[Create Credentials Access Keys](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html)
---

```sh
$ aws configure --profile <profile_name>

AWS Access Key ID [None]: <access_key_id>
AWS Secret Access Key [None]: <secret_access_key>
Default region name [None]: <region_name>
Default output format [None]: <text/json>
```

```sh
$ cat ~/.aws/credentials

[<profile_name>]
aws_access_key_id = <access_key_id>
aws_secret_access_key = <secret_access_key>

$ cat ~/.aws/config

[profile <profile_name>]
region = <region_name>
output = <text/json>
```

## Especifique o seu profile padrão (Linux & MacOS)

```sh
$ export AWS_PROFILE=<profile_name>
$ echo $AWS_PROFILE

# expected output
<profile_name>
```

## Especifique o seu profile padrão (Windows)

```sh
$ Set-Variable -Name "AWS_PROFILE" -Value "<profile_name>"
$ Get-Variable -Name "AWS_PROFILE"
# expected output
Name                           Value
----                           -----
AWS_PROFILE                    <profile_name>
```
