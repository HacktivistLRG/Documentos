# Secuencias de control

| №      | Acrónimo | Significado          | Secuencia | Descripción en inglés                    | Descripción en español                               |
|--------|----------|----------------------|-----------|------------------------------------------|------------------------------------------------------|
| 0      | Cc       | Carácter de control  | <NUL>     | NULL                                     | NULO                                                 |
| 1      | Cc       | Carácter de control  | <SOH>     | START OF HEADING                         | INICIO DE ENCABEZADO                                 |
| 2      | Cc       | Carácter de control  | <STX>     | START OF TEXT                            | INICIO DEL TEXTO                                     |
| 3      | Cc       | Carácter de control  | <ETX>     | END OF TEXT                              | FIN DE TEXTO                                         |
| 4      | Cc       | Carácter de control  | <EOT>     | END OF TRANSMISSION                      | FIN DE LA TRANSMISIÓN                                |
| 5      | Cc       | Carácter de control  | <ENQ>     | ENQUIRY                                  | CONSULTA                                             |
| 6      | Cc       | Carácter de control  | <ACK>     | ACKNOWLEDGE                              | RECONOCIMIENTO                                       |
| 7      | Cc       | Carácter de control  | <BEL>     | BELL                                     | CAPANA                                               |
| 8      | Cc       | Carácter de control  | <BS>      | BACKSPACE                                | RETROCESO                                            |
| 9      | Cc       | Carácter de control  | <HT>      | HORIZONTAL TABULATION                    | TABULACIÓN HORIZONTAL                                |
| 10     | Cc       | Carácter de control  | <LF>      | LINE FEED                                | AVANCE DE LINEA                                      |
| 11     | Cc       | Carácter de control  | <VT>      | VERTICAL TABULATION                      | TABULACIÓN VERTICAL                                  |
| 12     | Cc       | Carácter de control  | <FF>      | FORM FEED                                | AVANCE DE FORMULARIO                                 |
| 13     | Cc       | Carácter de control  | <CR>      | CARRIAGE RETURN                          | RETORNO DE CARRO                                     |
| 14     | Cc       | Carácter de control  | <SO>      | SHIFT OUT                                | CAMBIO HACIA AFUERA                                  |
| 15     | Cc       | Carácter de control  | <SI>      | SHIFT IN                                 | CAMBIO HACIA ADENTRO                                 |
| 16     | Cc       | Carácter de control  | <DLE>     | DATA LINK ESCAPE                         | ESCAPAR ENLACE DE DATOS                              |
| 17     | Cc       | Carácter de control  | <DC1>     | DEVICE CONTROL ONE                       | CONTROL DE DISPOSITIVO UNO                           |
| 18     | Cc       | Carácter de control  | <DC2>     | DEVICE CONTROL TWO                       | CONTROL DE DISPOSITIVO DOS                           |
| 19     | Cc       | Carácter de control  | <DC3>     | DEVICE CONTROL THREE                     | CONTROL DE DISPOSITIVO TRES                          |
| 20     | Cc       | Carácter de control  | <DC4>     | DEVICE CONTROL FOUR                      | CONTROL DE DISPOSITIVO CUATRO                        |
| 21     | Cc       | Carácter de control  | <NAK>     | NEGATIVE ACKNOWLEDGE                     | RECONOCIMIENTO NEGATIVO                              |
| 22     | Cc       | Carácter de control  | <SYN>     | SYNCHRONOUS IDLE                         | REPOSO SINCRÓNICO                                    |
| 23     | Cc       | Carácter de control  | <ETB>     | END OF TRANSMISSION BLOCK                | FIN DEL BLOQUE DE TRANSMISIÓN                        |
| 24     | Cc       | Carácter de control  | <CAN>     | CANCEL                                   | CANCELAR                                             |
| 25     | Cc       | Carácter de control  | <EM>      | END OF MEDIUM                            | FIN DEL MEDIO                                        |
| 26     | Cc       | Carácter de control  | <SUB>     | SUBSTITUTE                               | SUSTITUIR                                            |
| 27     | Cc       | Carácter de control  | <ESC>     | ESCAPE                                   | ESCAPAR                                              |
| 28     | Cc       | Carácter de control  | <FS>      | FILE SEPARATOR                           | SEPARADOR DE ARCHIVO                                 |
| 29     | Cc       | Carácter de control  | <GS>      | GROUP SEPARATOR                          | SEPARADOR DE GRUPO                                   |
| 30     | Cc       | Carácter de control  | <RS>      | RECORD SEPARATOR                         | SEPARADOR DE REGISTRO                                |
| 31     | Cc       | Carácter de control  | <US>      | UNIT SEPARATOR                           | SEPARADOR DE UNIDAD                                  |
| 127    | Cc       | Carácter de control  | <DEL>     | DELETE                                   | SUPRIMIR                                             |
| 128    | Cc       | Carácter de control  | <PAD>     | PADDING CHARACTER                        | CARÁCTER DE RELLENO                                  |
| 129    | Cc       | Carácter de control  | <HOP>     | HIGH OCTET PRESET                        | PREAJUSTE DE ALTO OCTECTO                            |
| 130    | Cc       | Carácter de control  | <BPH>     | BREAK PERMITTED HERE                     | SALTO PERMITIDO AQUÍ                                 |
| 131    | Cc       | Carácter de control  | <NBH>     | NO BREAK HERE                            | NO PERMITIR SALTO AQUÍ                               |
| 132    | Cc       | Carácter de control  | <IND>     | INDEX                                    | INDICE                                               |
| 133    | Cc       | Carácter de control  | <NL>      | NEXT LINE                                | SIGUIENTE LÍNEA                                      |
| 134    | Cc       | Carácter de control  | <SSA>     | START OF SELECTED AREA                   | INICIO DEL ÁREA SELECCIONADA                         |
| 135    | Cc       | Carácter de control  | <ESA>     | END OF SELECTED AREA                     | FIN DEL ÁREA SELECCIONADA                            |
| 136    | Cc       | Carácter de control  | <HTS>     | HORIZONTAL TABULATION SET                | CONJUNTO DE TABULACIÓN HORIZONTAL                    |
| 137    | Cc       | Carácter de control  | <HTJ>     | HORIZONTAL TABULATION WITH JUSTIFICATION | TABULACIÓN HORIZONTAL CON JUSTIFICACIÓN              |
| 138    | Cc       | Carácter de control  | <VTS>     | VERTICAL TABULATION SET                  | CONJUNTO DE TABULACIÓN VERTICAL                      |
| 139    | Cc       | Carácter de control  | <PLD>     | PARTIAL LINE DOWN                        | LÍNEA PARCIAL HACIA ABAJO                            |
| 140    | Cc       | Carácter de control  | <PLU>     | PARTIAL LINE UP                          | LÍNEA PARCIAL HACIA ARRIBA                           |
| 141    | Cc       | Carácter de control  | <RLF>     | REVERSE LINE FEED                        | AVANCE DE LÍNEA INVERSO                              |
| 142    | Cc       | Carácter de control  | <SS2>     | SINGLE SHIFT TWO                         | CAMBIO UNICO DOS                                     |
| 143    | Cc       | Carácter de control  | <SS3>     | SINGLE SHIFT THREE                       | CAMBIO UNICO TRES                                    |
| 144    | Cc       | Carácter de control  | <DCS>     | DEVICE CONTROL STRING                    | CADENA DE CONTROL DEL DISPOSITIVO                    |
| 145    | Cc       | Carácter de control  | <PU1>     | PRIVATE USE ONE                          | USO PRIVADO UNO                                      |
| 146    | Cc       | Carácter de control  | <PU2>     | PRIVATE USE TWO                          | USO PRIVADO DOS                                      |
| 147    | Cc       | Carácter de control  | <STS>     | SET TRANSMIT STATE                       | ESTABLECER ESTADO DE TRANSMISIÓN                     |
| 148    | Cc       | Carácter de control  | <CCH>     | CANCEL CHARACTER                         | CANCELAR CARÁCTER                                    |
| 149    | Cc       | Carácter de control  | <MW>      | MESSAGE WAITING                          | MENSAJE EN ESPERA                                    |
| 150    | Cc       | Carácter de control  | <SPA>     | START OF PROTECTED AREA                  | INICIO DEL ÁREA GUARDADA o INICIO DEL ÁREA PROTEGIDA |
| 151    | Cc       | Carácter de control  | <EPA>     | END OF PROTECTED AREA                    | FIN DEL ÁREA GUARDADA o FIN DEL ÁREA PROTEGIDA       |
| 152    | Cc       | Carácter de control  | <SOS>     | START OF STRING                          | INICIO DE CADENA                                     |
| 153    | Cc       | Carácter de control  | <SGCI>    | SINGLE GRAPHIC CHARACTER INTRODUCER      | INTRODUCIR CARÁCTER GRÁFICO ÚNICO                    |
| 154    | Cc       | Carácter de control  | <SCI>     | SINGLE CHARACTER INTRODUCER              | INTRODUCIR CARÁCTER UNICO                            |
| 155    | Cc       | Carácter de control  | <CSI>     | CONTROL SEQUENCE INTRODUCER              | INTRODUCIR SECUENCIA DE CONTROL                      |
| 156    | Cc       | Carácter de control  | <ST>      | STRING TERMINATOR                        | TERMINADOR DE CADENA                                 |
| 157    | Cc       | Carácter de control  | <OSC>     | OPERATING SYSTEM COMMAND                 | COMANDO DEL SISTEMA OPERATIVO                        |
| 158    | Cc       | Carácter de control  | <PM>      | PRIVACY MESSAGE                          | MENSAJE DE PRIVACIDAD                                |
| 159    | Cc       | Carácter de control  | <APC>     | APPLICATION PROGRAM COMMAND              | COMANDO DE PROGRAMA DE APLICACIÓN                    |
