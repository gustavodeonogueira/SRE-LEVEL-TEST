
#Construa o teste:
docker build -t sre-app:1.0.1 app/
docker run -p 8080:8080 sre-app:1.0.1

#Execute:
cd tests && pytest -v

#Execute o deploy:
./deploy.sh 1.0.1

#Monitore a aplicação:
./monitor.sh

#Como fazer rollback
Se algo der errado após o deploy:

#Execute o rollback:
./rollback.sh

#Copiar código
Verifique se a versão anterior voltou:
curl http://localhost:8080/health