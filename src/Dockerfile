# Quando vamos criar uma imagem, usamos uma imagem base que já tenha uma estrutura inicial de sistema de arquivos e as dependências necessárias.
# Aqui, escolhemos uma imagem oficial do Node.js, que já possui o Node.js e o npm instalados.
FROM node:22.6.0

# Define o diretório de trabalho dentro do contêiner. Todas as operações subsequentes serão executadas dentro deste diretório.
# Isso ajuda a organizar os arquivos da aplicação e isolar o ambiente.
WORKDIR /app

# Copia os arquivos 'package.json' e 'package-lock.json' (caso exista) do diretório atual no host para o diretório de trabalho dentro do contêiner.
# Isso é importante para garantir que as dependências listadas nesses arquivos sejam instaladas.
COPY package*.json ./

# Executa o comando 'npm install' dentro do contêiner para instalar todas as dependências listadas no arquivo 'package.json'.
# Essas dependências são instaladas no diretório 'node_modules' dentro do contêiner.
RUN npm install

# Copia todos os arquivos e diretórios do diretório atual (host) para o diretório de trabalho no contêiner.
# Isso inclui o código-fonte da aplicação e quaisquer outros arquivos necessários para a execução.
COPY . .

# Informa ao Docker que a aplicação irá escutar na porta 8080.
# Essa linha é uma documentação e não expõe automaticamente a porta, mas indica que o contêiner vai usar essa porta para comunicação.
EXPOSE 8080

# Especifica o comando que será executado quando o contêiner for iniciado.
# Neste caso, estamos iniciando o servidor Node.js usando o arquivo 'server.js'.
CMD ["node", "server.js"]
