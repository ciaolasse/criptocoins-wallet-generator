# Gerador de Carteiras Bitcoin em Node.js

Este projeto implementa um gerador de carteiras Bitcoin usando Node.js com as bibliotecas `bip32`, `bip39` e `bitcoinjs-lib`. Ele cria carteiras HD (Hierarchical Deterministic), conforme os padrões BIP32/BIP39, para geração de chaves e endereços seguros na rede Bitcoin. Por padrão, utiliza-se a rede de teste (testnet), facilitando o desenvolvimento e testes sem Bitcoins reais.

## Funcionalidades

1. **Importação de Dependências**: O código usa três bibliotecas fundamentais:
   - `bip32`: Implementa o BIP32 para a criação de carteiras HD.
   - `bip39`: Gera frases mnemônicas com suporte aos padrões de segurança Bitcoin.
   - `bitcoinjs-lib`: Biblioteca principal para manipulação de elementos Bitcoin, como chaves e endereços.

2. **Definição da Rede**: A carteira é configurada para a rede de teste (`testnet`), permitindo testes seguros de desenvolvimento. É possível modificar para a rede principal (`mainnet`).

3. **Definição do Caminho de Derivação**: O caminho de derivação segue o padrão BIP44 para carteiras HD, estruturado para gerar múltiplas contas e endereços. O caminho padrão `m/44'/1'/0'/0` permite derivar várias carteiras a partir de uma única seed.

4. **Geração do Mnemonic**: A biblioteca `bip39` gera uma frase mnemônica de 12 a 24 palavras, fácil de lembrar e armazenar, que serve como base para a seed.

5. **Conversão do Mnemonic para Seed**: A frase mnemônica é convertida em uma seed binária, que será usada na derivação das chaves da carteira.

6. **Criação da Raiz da Carteira HD**: A partir da seed, é criada a raiz de uma carteira HD, que serve como ponto inicial para derivação das chaves subsequentes. Esta abordagem permite segurança e flexibilidade para gerar novos endereços a partir de uma raiz.

7. **Derivação da Conta e Chaves**: Deriva-se uma conta a partir da raiz, e então uma chave pública e privada para um endereço específico.

8. **Geração do Endereço Bitcoin**: A chave pública derivada é utilizada para gerar um endereço Bitcoin no formato P2PKH (Pay-to-PubKey-Hash), amplamente utilizado e compatível com diversas carteiras e exchanges.

9. **Exibição das Informações**: O código exibe as seguintes informações no console:
   - **Endereço Bitcoin**: Endereço P2PKH para recebimento de Bitcoin.
   - **Chave Privada (WIF)**: Chave privada em formato WIF (Wallet Import Format), podendo ser importada para outras aplicações.
   - **Frase Mnemônica**: A frase de recuperação da carteira.

## Passo a Passo para Execução

1. **Instale as Dependências**: Certifique-se de que `bip32`, `bip39` e `bitcoinjs-lib` estejam instalados.
2. ```bash
   npm install bip32 bip39 bitcoinjs-lib
3. **Execute o Gerador de Carteiras**: Com as dependências instaladas, execute o script:
4. ```bash
   node createWallet.js
5. **Verifique a Saída**: O console mostrará o endereço Bitcoin, a chave privada e a frase mnemônica.

## Estrutura do Código

Este projeto possui uma estrutura modular e documentada para fácil compreensão e manutenção, com cada etapa detalhada para orientação do desenvolvedor.

## Considerações de Segurança

Frase Mnemônica: A frase mnemônica deve ser mantida em sigilo, pois permite a recuperação da carteira e dos fundos associados.
Chave Privada: Nunca compartilhe a chave privada, pois ela garante acesso total aos fundos da carteira.
Testnet: Este projeto está configurado para a testnet, adequada para testes. Não utilize em produção sem ajustar para a mainnet.
Este gerador é ideal para desenvolvedores interessados em aprender sobre a criação de carteiras Bitcoin e a estrutura das carteiras HD com BIP32/BIP39.


   
