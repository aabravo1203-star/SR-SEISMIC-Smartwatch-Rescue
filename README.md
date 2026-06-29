SR-SÍSMICA: SOFTWARE DE RESCATE Y BALIZA
INALÁMBRICA AUTOMATIZADA PARA SMARTWATCHES
EN CATÁSTROFES SÍSMICAS
Repositorio Oficial: Arquitectura Global, Viabilidad Hardware y Flujo de Contingencia Multi-Capa.
Parte I: Diagrama de Flujo del Desarrollo (El Qué)
El núcleo del software opera bajo un protocolo cronológico estricto diseñado para escenarios de sismos
colapsivos de gran escala, optimizando cada fase física y electromagnética del reloj inteligente:
1. 
2. 
3. 
4. 
5. 
6. 
7. 
Recepción de Alerta de Sismo: El dispositivo inteligente captura en tiempo real la notificación oficial
del sistema (ej. Google Earthquake Alerts System). El evento funciona como un disparador (Trigger)
por hardware que inicializa el software en modo latente de alta prioridad.
Modo Caja Negra (Registro de Impacto): Durante e inmediatamente después de las vibraciones
mecánicas del sismo, el software almacena en una base de datos embebida de alta velocidad
(SQLite/Room) las métricas vectoriales de los acelerómetros axiales, giroscopio, barómetro y
sensores ópticos de pulso. Esto registra con exactitud biomédica el trauma por impacto sufrido por la
víctima durante el colapso.
Transición a Supervivencia de Batería: Tras una ventana prudencial definida por especialistas en
gestión de emergencias sísmicas (con el fin de dar tiempo al uso de redes de telefonía y Wi-Fi
convencionales por civiles conscientes), el sistema operativo apaga de manera selectiva todos los
hilos, pantallas y transceptores redundantes. Se configura un entorno exclusivo para el soporte
extendido de la baliza.
Inicio del Sistema Faro: El reloj inicia la emisión de pulsos inalámbricos abiertos utilizando el
espectro de Bluetooth de Baja Energía (BLE), empaquetando identificadores de usuario, signos
vitales y datos barométricos, en perfecta armonía con destellos AMOLED overclockeados y
frecuencias acústicas audibles estandarizadas.
Mantenimiento Intermitente: El dispositivo cicla de forma automatizada entre suspensión profunda
(Deep Sleep) de hardware y ventanas activas de ráfagas de emisión. Este intervalo está balanceado
para proveer una ventana operativa mínima de rescate de 72 a 96 horas continuas.
Arribo de Rescatistas y Captura de Faros BLE: Al desplegarse en la zona cero, la app del
rescatista intercepta de manera pasiva y masiva los paquetes libres de BLE sin requerir interacción o
emparejamiento con el dispositivo soterrado, estructurando un mapa de víctimas potenciales en el
cuadrante.
Triage Automatizado por Parámetros Médicos: Algoritmos avanzados procesan en segundos el
estado vital de los paquetes de datos recibidos y los clasifican de forma cromática: Víctimas Fatales
(ausencia de dinámica cardíaca y motriz), Atrapados Estables y Atrapados Críticos (bradicardia,
SR-SÍSMICA: Software de Rescate y Baliza Inalámbrica
1
taquicardia o desaturación severa de oxígeno por aplastamiento), ordenando de manera matemática
las prioridades de excavación de las brigadas.
8. 
9. 
10. 
11. 
Señal Receptor-Emisor "Te Vi": La interfaz del rescatista envía de forma dirigida un comando de
confirmación (ACK_TE_VI). Al recibirse en la micro-ventana de apertura de radio del smartwatch, el
software altera instantáneamente su reloj interno y eleva la frecuencia de los pitidos y las emisiones
lumínicas (ej. cada 15 segundos) para consolidar el rastreo micro-espacial.
Rastreo Direccional de Proximidad: La fuerza de señal de radio (RSSI) actúa bajo el principio
analógico de la telemetría biológica, guiando de forma auditiva y visual al rescatista a través de las
coordenadas superficiales X e Y.
Radar Activo (Profundidad Z y Caracterización de Escombros): En el punto de máxima ganancia
electromagnética, el celular del rescatista ejecuta un pulso calibrado. El reloj devuelve su estampa
temporal física y su potencia de recepción, posibilitando al algoritmo deducir mediante Tiempo de
Vuelo (ToF) y degradación de potencia el eje Z exacto y la densidad estructural (losa densa de
hormigón armado vs. cavidad habitable).
Contención Psicológica Pasiva: Al validar la viabilidad del rescate, la app del rescatista inyecta un
comando prioritario de audio en el altavoz del smartwatch, reproduciendo un mensaje de contención
pregrabado a máxima potencia: "Ya te localizamos. El equipo de rescate está trabajando en la
superficie para sacarte. Mantené la calma".
Parte II: Fundamentos Técnicos y Análisis de Viabilidad (El Cómo)
1. Módulo de Overclocking de Hardware y Gestión Térmica
La viabilidad de este sistema radica en la alteración del Ciclo de Trabajo (Duty Cycle). Al aplicar Pulsos
Ultracortos, las restricciones térmicas estándar quedan anuladas por las leyes de la termodinámica de
semiconductores.
A. Pantalla AMOLED y Sobrealimentación Lumínica
Los paneles restringen su brillo continuo a unos 3.000 nits de fábrica. El umbral de destrucción
molecular inmediata de los diodos orgánicos está en los 5.000 nits. Al forzar un sobrevoltaje en el
microcontrolador del panel por un lapso de T_{on} = 50 ms, el calor generado sigue la ecuación:
E_{th} = I2 × R × T_{on}
Con un tiempo de enfriamiento de T_{off} = 600.000 ms (10 minutos), el calor acumulado en los
materiales orgánicos y en las celdas de litio adyacentes es insignificante. Esto permite una disipación
total por conducción y un destello estroboscópico de máxima intensidad de lúmenes reales útiles en la
oscuridad sísmica.
SR-SÍSMICA: Software de Rescate y Baliza Inalámbrica
2
B. Altavoz y Saturación Acústica
Para mitigar el sobrecalentamiento por efecto Joule en la bobina de los transductores piezoeléctricos o
dinámicos, el software inyecta ondas cuadradas o sinusoidales puras en ráfagas transitorias de
milisegundos. El diafragma se desplaza a su máxima excursión mecánica al 100% de su capacidad de
presión acústica sin peligro de fusión por fatiga térmica o eléctrica.
2. Módulo Acústico: Frecuencia Estandarizada y Propagación en
Estructuras Sísmicas
La frecuencia del pitido se fija de manera invariable en el rango de 3.5 kHz a 4 kHz (3500 a 4000 Hertz)
fundamentada bajo un diseño de Triple Coincidencia Óptima:
• 
• 
• 
Aislamiento Digital de Ruido (Software): El ruido pesado de la maquinaria de rescate y colapsos
estructurales opera por debajo de 1 kHz. Un pitido puro a 3.5 kHz se aísla mediante un filtro digital
de banda estrecha (Band-pass Filter) en el teléfono del rescatista, suprimiendo mecánicamente el
95% del ruido ambiente de la zona.
Sensibilidad Canina (K9): El aparato auditivo de los canes de búsqueda es altamente sensible a los
estímulos agudos en el espectro medio-alto (1 kHz a 8 kHz), acelerando el marcaje orgánico sobre el
terreno sísmico.
Resonancia Anatómica del Rescatista: El conducto auditivo humano externo posee una longitud
física que resuena de forma natural ante ondas de 3.5 kHz a 4 kHz. Esto provoca una amplificación
mecánica pasiva en el tímpano de entre 10 y 15 decibelios, incrementando exponencialmente el
rango de audición de las brigadas humanas sin requerir mayor potencia eléctrica del reloj.
3. Módulo de Radiofrecuencia (BLE): Sistema de Telemetría y Rastreo RSSI
El software convierte al microchip inalámbrico en un transmisor puro de paquetes de publicidad
(Advertising Packets) de BLE omnidireccionales y libres. La aplicación del rescatista calcula la pérdida
de propagación a través del RSSI medido en dBm, transformándolo en un indicador acústico iterativo
(Tic-Tic-Tic).
Dada la alta absorción de la mampostería y el hormigón armado sobre la banda de 2.4 GHz, la señal
experimenta caídas drásticas. Sin embargo, esta atenuación física se aprovecha como filtro de
precisión: la radiofrecuencia solo escapará con claridad por las micro-fisuras de aire de la estructura. Al
trazar un barrido en cruz en la superficie, el punto exacto que registre un pico vertical de potencia (ej. de-95 dBm a -65 dBm) y dispare el Tic-Tic hasta un zumbido continuo marcará con precisión milimétrica la
coordenada (X, Y) de la persona atrapada.
SR-SÍSMICA: Software de Rescate y Baliza Inalámbrica
3
4. Módulo de Radar Activo: Detección de Profundidad Z y Densidad
Estructural
Integra una lógica de ecolocalización electromagnética transmedia bidireccional basada en dos
variables analíticas concurrentes:
1. Cálculo de Distancia y Profundidad Física (Tiempo de Vuelo - ToF)
A partir de un haz emitido con una potencia conocida por el software (P_{emitida} = +20 dBm) desde
el celular del rescatista, el reloj captura el pulso y computa el microsegundo exacto de arribo
mediante un Hardware Timestamp junto a la potencia de recepción (P_{recibida}). Al responder con
estas métricas embebidas, la app del rescatista deduce el tiempo neto de viaje descartando la
latencia del procesador interno (T_{proc}):
Tiempo de Viaje = T_{total} - T_{proc}
Aplicando la velocidad de la luz (c), el retraso microelectrónico calcula la distancia lineal real o
profundidad absoluta en metros (Eje Z).
2. Cálculo de Densidad de la Estructura (Pérdida de Propagación)
El software analiza la caída neta de potencia (ΔP = P_{emitida} - P_{recibida}). Si el Tiempo de
Vuelo dicta que la víctima se localiza a 3 metros de distancia en línea recta, pero la pérdida
electromagnética (ΔP) es masiva (ej. una caída de 60 dB), el algoritmo procesa la discrepancia e
infiere que el medio obstructivo está compuesto por bloques sólidos y compactos de hormigón
armado y metalurgia. Si la caída se ajusta de manera exacta a la ley de la inversa del cuadrado,
dictamina la existencia de un espacio hueco o burbuja de aire vital.
5. Módulo Reactivo por Interrupción Lumínica (Efecto Linternazo)
El sensor de luz ambiental (ALS) del reloj inteligente monitoriza el entorno confinamiento en modo
pasivo analógico de ultra bajo consumo. El software discrimina variaciones lentas de luz solar, pero
implementa un filtro de pendientes dinámicas que detecta deltas rápidos de luminosidad (ΔL/Δt)
inferiores a los 200 ms. Cuando una brigada de rescate barre las grietas superficiales con focos tácticos
de alta potencia en un entorno de oscuridad total (<5 lux), el sensor genera una interrupción por
hardware (Hardware Interrupt). Esta señal despierta instantáneamente al procesador principal,
abortando el retraso de los 10 minutos para inicializar alertas de audio continuas y ráfagas máximas de
datos de radio durante 60 segundos.
