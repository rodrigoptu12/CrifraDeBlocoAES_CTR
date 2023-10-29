# Cifra de Bloco AES e Modo de Operação CTR - README

**Autor**
Rodrigo Pereira Couto
Matrícula: 190116510

**Descrição**
Este é um código que implementa a Cifra de Bloco AES (Advanced Encryption Standard) em conjunto com o Modo de Operação CTR (Counter). A Cifra de Bloco AES é um algoritmo de criptografia simétrica amplamente utilizado para proteger dados eletrônicos. O modo de operação CTR transforma o AES em um cifrador de fluxo, tornando-o adequado para criptografia de dados em blocos de tamanho fixo.

**Requisitos**
- Python 3.x

**Funcionamento**
O código opera da seguinte forma:

**AES (Cifra de Bloco Avançada)**
- O AES opera em um arranjo de 4x4 bytes chamado estado, inicialmente preenchido com o texto simples.
- O código usa uma chave de criptografia de 128, que é expandida em um conjunto de subchaves usando o planejamento de chave AES.
- O AES aplica um número de rodadas ao estado, consistindo de quatro etapas: SubBytes, ShiftRows, MixColumns e AddRoundKey. A última rodada omite a etapa MixColumns.
- O resultado final é o texto cifrado.

**Modo de Operação CTR (Counter)**
- Divide o texto simples em blocos do tamanho do bloco do cifrador.
- Inicializa um contador com um valor inicial e um vetor de inicialização (IV) exclusivo.
- Usa o planejamento de chave AES para expandir a chave de criptografia em um conjunto de subchaves.
- Para cada bloco, cria um nonce concatenando o IV com o contador e criptografa o nonce usando a subchave da rodada atual.
- Combina os bytes criptografados com o texto simples usando a operação XOR bit a bit.
- Incrementa o contador e repete até que todos os blocos tenham sido processados.

**Uso**
- Este código aceita imagens no formato .bmp e arquivos de texto (.txt) como entrada para criptografia no modo CTR.
- É necessário definir a chave de criptografia no código. ex : ( 0x54 0x68 0x61 0x74 0x73 0x20 0x6d 0x79 0x20 0x4b 0x75 0x6e 0x67 0x20 0x46 0x75 ) 
- O número de rodadas do AES pode ser configurado na chamada. Recomenda-se testar diferentes números de rodadas para avaliar a segurança e desempenho da criptografia.
