import random
#aqui importare un libreria para los colores


def color_al_azar():
     opción_color = random.randint (1,4)
     if opción_color == 1:
         color = "rojo"
     elif opción_color == 2:
         color = "amarillo"
     elif opción_color == 3:
         color = "azul"
     else:
         color = "verde"
     return color

def repartir_mazo(cantidad):
    mazo = ""
    contador = 0
    while contador < cantidad:
      color = color_al_azar() 
      numero = random.randint(0,9)
      mazo = mazo + color + " " + str(numero) +  ", "
      contador = contador + 1
    return mazo
    
def robar_carta():
    color = color_al_azar()
    numero = random.randint(0,9)
    return color, numero

def es_valida(color_elegido,numero_elegido,color_actual,numero_actual):
    color_igual = color_elegido == color_actual
    numero_igual = numero_elegido == numero_actual
    if color_igual or numero_igual:
        return True
    else:
        return False
    
def turno_del_jugador(color_actual,numero_actual):
    color_elegido = input("Cual es el color de tu carta")
    numero_elegido = int(input("Cual nuemero eliges"))
    # poner una forma en revisar que la carta la tenga el jugador
    # tambien que despues esa carta se quite de su mazo
    return es_valida(color_elegido,numero_elegido,color_actual,numero_actual)


def turno_de_la_maquina(color_actual,numero_actual):
    # hacer algo para que la computadora vea si tiene una carta que coincida con la funcion es_valida
    #la juega y se le resta 1 a su mazo
    print("es turno de la computadora")
    
def calcular_puntaje(mazo_del_jugador,mazo_de_la_maquina):
    #poder sumar y restar las cartas que quedaron en cada mazo
    print("se calculara el puntaje final")
    
def mostrar_resultado(ganador, cartas_restantes_perdedor, num_turno):
    print("y el ganador es: ", ganador)
    print("el perdedor se quedo con: ", cartas_restantes_del_perdedor)
    print("estos fueron los turnos de la partida")
    
def jugar():
    color_actual = color_al_azar()
    numero_actual = random.randint (0,9)
    print ("carta en la mesa: ", color_actual, numero_actual)
    
    mazo_jugador = repartir_mazo(7)
    mazo_maquina = repartir_mazo(7)
    cartas_del_jugador = 7
    cartas_de_la_maquina = 7
    turno_actual = "jugador"
    num_turno = 1
    #queda pendiente hacer que que pasaria cuando alguien se quede sin cartas osea me falta unas coasa del turno de la maquina que le pueda bajar el contador y que sepa cuales tiene asi que en este caso
    #depende de las jugadas del jugador
    while cartas_del_jugador > 0 and cartas_de_la_maquina > 0 and num_turno <= 6:
        print("Turno", num_turno, "de", turno_actual)
        if turno_actual == "jugador":
            print("estas son tus cartas: ", mazo_jugador)
            if turno_del_jugador(color_actual,numero_actual):
                cartas_del_jugador = cartas_del_jugador - 1
                print("la jugada es valida")
                #queda que ahora esa carte forme parte de las cartas de la mesa (en este caso que seria?, chance la consola)
            else:
                carta_robada = robar_carta()
                #  falta que ahora que la carta robada se agregue al mazo
                cartas_del_jugador = cartas_del_jugador + 1
                print("mas suerte para la proxima, roba una carta", carta_robada)
            turno_actual = "maquina"
            
        else:
            turno_de_la_maquina(color_actual,numero_actual)
            turno_actual = "jugador"
            num_turno = num_turno + 1
    if cartas_del_jugador < cartas_de_la_maquina:
        ganador = "jugador"
        cartas_restantes_del_perdedor = cartas_de_la_maquina
    elif cartas_de_la_maquina < cartas_del_jugador:
        ganador = "computadora"
        cartas_restantes_del_perdedor = cartas_del_jugador
    else:
        ganador = "empate"
        cartas_restantes_del_perdedor = cartas_del_jugador
        
    mostrar_resultado(ganador, cartas_restantes_perdedor, num_turno - 1)
    calcular_puntaje(mazo_del_jugador,mazo_de_la_maquina) 
    
def main():
    opcion = 0
    while opcion !=3:
        print(" 1. jugar UNO")
        print(" 2. instrucciones")
        print (" 3. salir")
        opcion = int(input("elige una opcion: "))
        match opcion:
            case 1:
                jugar()
            case 2:
                print(" es jugar el juego de mesa UNO pero muy basico sin nada de come +2, +4, ni cambios de colores etc")
            case 3:
                print( "wow no pense que de verdad pusieras 3 y si fue asi pues adios")
            case _:
                print(" esto ni siquiera estaba como opciones")

main()
