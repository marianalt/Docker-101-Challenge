FROM node:16.14.0
#-slim     acrescentar no fim da linha anterior -> a docker image diminui de tamanho (correr docker images)
#as build  melhora

WORKDIR /app/frontend
#chamar nome q se quiser; se nao existir ele cria

RUN npm install
# fazer o run antes do copy melhora mt o tempo de build pq as dependencias do npm install n costumam mudar tnt, enquanto o codigo vai mudando mt

COPY . .
#nao se pode ter aqui outro workdir senao sais do sitio onde ele faz cenas e vais para outro e ele vê q n esta no sitio onde se fez as coisas

ENTRYPOINT [ "npm", "start" ]