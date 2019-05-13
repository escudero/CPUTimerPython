# CPUTimerPython
Fork da classe CPUTimerPython da disciplina INF2926 (2019.1) para algumas adaptações.

## Funcionalidades
    
<b>start():</b>

    Inicia a medição/cronometragem

<b>stop():</b>

    Pausa a medição/cronometragem

<b>remove_last_lap():</b>

    Remove o último lap, mas só pode ser chamado apenas 1x e quando estiver no stop.

<b>lap(start_stopped = False):</b>

    Para a medição/cronometragem atual e inicia uma nova.

    start_stopped = "FALSE":
        Imediamente inicia a nova cronometragem
    start_stopped != "FALSE":
        A nova cronometragem inicia-se pausada

<b>reset():</b>

    Reseta variaveis internas e prepara inst�ncia da classe para uma
    nova bateria de cronometragems

<b>get_time(reference = "total", unit = "seconds"):</b>

    Retorna a cronometragem armazenada de acordo com a refer�ncia e
    unidade requerida.

    reference = "total" ou "t":
        tempo total
    reference = "average" ou "avg" ou "a":
        tempo médio
    reference = "last" ou "l":
        tempo da última medição
    reference = "first" ou "f":
        para detail_level > 0, tempo da primeira medição
    reference = <inteiro>
        para detail_level > 0, tempo da medição de numero <inteiro>
        
    unit = "seconds" ou "sec" ou "s":
        retorna a medição em segundos
    unit = "minutes" ou "min" ou "m":
        retorna a medição em minutos
    unit = "hours" ou "hr" ou "h":
        retorna a medição em horas
    unit = "milliseconds" ou "millisec" ou "milli" ou "ms":
        retorna a medição em mili segundos
    unit = "microseconds" ou "microsec" ou "micro" ou "us":
        retorna a medição em micro segunds         
        
    Retorna: valor da medição requerida em float    

<b>get_stamp(reference = "total" , style = "clock" , ignore_zeroes = False):</b>

    Retorna um string da estampa de tempo de uma cronometragem de
    acordo com uma referencia e um estilo definido.

    reference = "total" ou "t":
        tempo total
    reference = "average" ou "avg" ou "a":
        tempo médio
    reference = "last" ou "l":
        tempo da última medição
    reference = "first" ou "f":
        para detail_level > 0, tempo da primeira medição
    reference = <inteiro>
        para detail_level > 0, tempo da medição de numero <inteiro>
        
    style = "clock":
        formato:
        HH:mm:ss.SSSS
        Legenda:
        <horas>:<minutos>:<segundos>.<milisegundos>      
    style = "si" ou "SI":
        formato:
        <hora>h <minuto>m <segundo>s <milisegundo>ms <microsegundo>us
        
    ignore_zeroes = False:
        Retorna todas as unidades de tempo 
    ignore_zeroes = True:
        Não retorna unidades de tempo iguais a zero
        
    Retorna: string da estampa de tempo

<b>auto_loop(function, repetitions = 1000000):</b>

    Mede a função passada várias vezes seguidas
    Apenas um wrapper da timeit.timeit

    function = <nome da função>:
        função a ser executada
        
    repetitions = <inteiro>:
        Quantidade de vezes a se executar a função

    Obs.:
    A chamada dessa função automaticamente tornará o detail_level = 0
