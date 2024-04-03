# estudospython-
aqui estou estudando pelo youtube com a hastag!
#passo a passo do projeto
#passo 1 : entrar no sistema da empreza !
  
import pyautogui
import time

pyautogui.PAUSE = 0.5

#principais comando do pyautogui
#pyautogui.click -> clicar em algum lugar da tela 
#pyautogui.write -> escrever um texto
#pyautogui.press -> pressionar 1 tecla do teclado

#abrir o navegador 
pyautogui.press('win')
pyautogui.write('chrome')  
pyautogui.press('enter')

#entrar no site !
link = 'https://dlp.hashtagtreinamentos.com/python/intensivao/login'
pyautogui.write(link)
pyautogui.press('enter')

#pausa um pouco maior ( 3 segundos )
time.sleep(3)

#passo 2 : fazer login :
pyautogui.click(x=602, y=554)
pyautogui.write('pablo_zy@hotmail.com')

#escrever a senha e entrar no sistema !
pyautogui.press('tab')
pyautogui.write('Pablo210889@')
pyautogui.press('tab')
pyautogui.press('enter')
time.sleep(2)

#passo 3 : importar a base de dados 
import pandas
tabela = pandas.read_csv('produtos.csv')
print(tabela)

#passo 4 : cadastrar 1 produto
#para cada linha da minha tabela
for linha in tabela.index:
#clicar no primeiro campo
    pyautogui.click(x=810, y=380)

    #codigo do produto :
    codigo = tabela.loc[linha, 'codigo']
    pyautogui.write(tabela.loc[linha,'codigo'])
    pyautogui.press('tab')

    #marca do produto 
    pyautogui.write( tabela.loc[linha, 'marca'])
    pyautogui.press('tab')

    #tipo de produto 
    pyautogui.write(tabela.loc[linha, 'tipo'])
    pyautogui.press('tab')

    #categoria
    pyautogui.write(str(tabela.loc[linha, 'categoria']))
    pyautogui.press('tab')

    #preço unitario 
    pyautogui.write(str(tabela.loc[linha, 'preco_unitario']))
    pyautogui.press('tab')

    #custo
    pyautogui.write(str(tabela.loc[linha,'custo']))
    pyautogui.press('tab')

    #obs
    obs = tabela.loc[linha, 'obs']
    if not pandas.isna(obs):
        pyautogui.write(tabela.loc[linha,'obs'])
    pyautogui.press('tab')


    #enviar
    pyautogui.press('enter')
    pyautogui.scroll(10000)

