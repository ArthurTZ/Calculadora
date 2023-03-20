### Calculadora
Calculadora Python com Tkinter
- Passo a passo que  descreve como criar uma calculadora básica em Python usando o Tkinter.

## Pré-requisitos:
  Antes de começar, certifique-se de que você tenha o Python


### Importando as Bibliotecas:
    from tkinter import *
    from tkinter import ttk
    from turtle import right

### em seguida começa-se com as cores para melhor vizualização da calculadora:
    #cores

    cor1 = "#1e1f1e"  #preta
    cor2 = "#feffff"  # Branco
    cor3 = "#38576b"  #azul
    cor4 = "#ECEFF1"  #cinza
    cor5 = "#FFAB40"  # laranja

## O tkinter é bem simples, entao a criação de sua tela é da seguinte maneira:
    # tamanho da tela,cor e titulo
    janela = Tk()
    janela.title('Calculadora')
    janela.geometry('235x310')
    janela.config(bg=cor1)

    #frames/quadros.
    frame_tela = Frame(janela, width=235, height=50, bg=cor3)
    frame_tela.grid(row=0, column=0)

    frame_corpo = Frame(janela, width=235, height=268)
    frame_corpo.grid(row=1, column=0)
    
 ### penultimo passo sao as funções para o funcionamento da calculadora:
    #funçao para o calculo
    def calcular():
        global todos_valores
        resultado = eval(todos_valores)
        valor_texto.set(str(resultado))


    #funçao para limpar o calculo
      def limpar():
          global todos_valores
          todos_valores = ''
          valor_texto.set('')


      app_label = Label(frame_tela, textvariable=valor_texto, width=16, height=2,padx=7, relief=FLAT, anchor="e",justify=RIGHT, font=('Ivy 18'), bg=cor3, fg=cor2)
      app_label.place(x=0, y=0)
      
### Por fim, os seus botões:
      #Botoes
      b_1 = Button(frame_corpo, command= limpar ,text="C", width=11, height=2, bg=cor4,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
      b_1.place(x=0, y=0)
      b_2 = Button(frame_corpo,command=lambda:entrar_valores('%'), text="%", width=5, height=2, bg=cor4,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
      b_2.place(x=118, y=0)
      b_3 = Button(frame_corpo,command=lambda:entrar_valores('/'), text="/", width=5, height=2, bg=cor5,fg=cor2,font=('Ivy 13 bold'), relief=RAISED, overrelief=RIDGE)
      b_3.place(x=177, y=0)
 
      janela.mainloop()
 
 ### Para não ficar grande, é so repetir e mudar nomes dos botões e suas numerações e operações matematicas
