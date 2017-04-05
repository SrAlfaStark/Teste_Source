# coding: utf-8
#feito por noah augusto
#AlfaStark

import smtplib

serve = smtplib.SMTP('smtp.gmail.com', 587)
serve.ehlo()
serve.starttls()

user = str(input("digite seu email: "))
senha = str(input("digite sua senha: "))
to = str(input("digite o email que  deseja enviar a mensagem: "))
numero = int(input("digite a quantidade de email que voce deseja enviar: "))
msg = str(input("digite a mensagem que voce deseja enviar: "))

try:
    serve.login(user, senha)
    print ("logado com sucesso")
except:
    print ("email ou senha invalidos ou voce precisa dar permissao no seu email")
x = 0

while(x<numero):
    serve.sendmail(user, to, msg)
    x=x+1
    print ("enviado", x, "email")
