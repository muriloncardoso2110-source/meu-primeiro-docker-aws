Lab de Docker 🐳
Fiz esse projeto pra parar de sofrer com ambiente local e começar a entender como o Docker funciona na prática, e depois subir na AWS

O que tem aqui:
É um servidor Nginx rodando um HTML simples. Usei a imagem Alpine porque é muito mais leve que as outras.

🧠 Sobre o que eu aprendi estudando essa parte:
Caminho das pastas: No começo o site não abria. Descobri que o Nginx no Alpine usa o caminho /usr/share/nginx/html/ e não o /var/www/html/ que eu tava acostumado.

Imagem pesada: Tentei fazer com Python primeiro, mas a imagem ficou grande. Com Nginx e Alpine ficou minúscula, o que é bem melhor pra economizar na nuvem.

Portas: Demorei um pouco pra entender que a porta de "dentro" do container tem que ser mapeada pra "fora".

Como rodar:
Bash
# Faz o build
docker build -t meu-app .

# Roda (acessa em localhost:8080)
docker run -d -p 8080:80 meu-app
Próximo passo: Tentar automatizar isso com GitHub Actions pra jogar direto pro ECR da AWS.

Dica pro Git:
Na hora de dar o git commit, não precisa ser tudo formal tipo "Initial Commit". Pode mandar uns:

git commit -m "subindo o básico do html"

git commit -m "ajustando o dockerfile que tava dando erro de pasta"
