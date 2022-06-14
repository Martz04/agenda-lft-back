
# Requerimientos Funcionales
Aplicacion que permite al Doctor y Administradores agendar citas a sus pacientes para ser tratador por un fisioterapeuta.

## UC1: Horario de LFT
Como Administrador, Doctor o LFT,
Quiero agregar el horario disponible de los LFT para recibir pacientes.
De tal manera que puedan los doctores agendar citas dentro de ese horario y de mi especialidad.

## UC2: Registrar vacaciones
Como Administrador, Doctor o LFT,
Quiero agregar los dias de vacaciones del LFT
De tal manera que aunque sea de la especialidad o dentro del horario, si el LFT esta de vacaciones, no se le asigne ningun paciente.

## UC3: Confirmar terapia
Como LFT,
Dado que estoy dentro de mi horario de terapias
Quiero recibir una confirmacion de la cita de un pacientepor SMS o email.
De tal manera que cuando el doctor agende una cita hacia mi horario yo tenga conocimiento de ella.

## UC4: Rechazar terapia
Como LFT,
Dado que tengo una cita agendada en esta semana
Quiero recazar dicha cita
De tal manera que el sistema pueda reubicar a otro LFT disponible o en su defecto notificar al Paciente de la cancelacion de la cita.

## UC5: Crear Cita
Como Doctor,
Quiero agendar uno o mas pacientes a la siguiente fecha disponible del LFT de la especialidad
De tal manera que la cita o las citas queden calendarizadas y yo tenga conocimiento de los LFTs que se asignaron.

## UC6: Reagendar Terapeuta
Como Sistema,
Dado que se rechaza una terapia
Quiero reagendar en la misma fecha y hora a otro LFT disponible
De tal manera que el paciente no sufra cambios en su terapia.

## UC7: Reagendar Terapeuta - fallo
Como Sistema,
Dado que se rechaza una terapia y no hay LFT disponible
Quiero cancelar la cita del dia y hora.
De tal manera que el doctor y el paciente tengan conocimiento de la cancelacion.

# Roles
* LTF Fisioterapeuta
* Doctor
* Paciente

![use-cases](/architecture/UML/use-cases.png)

## Initial Conversation 25/05/2022

Necesito una agenda para otorgar citas en bloque personalizable a número de sesiones y por días de la semana por terapeuta (son como 10 de turno matutino e igual vespertino)

Por ejemplo Mario da terapia de mano lunes y jueves, de pie martes y viernes pero de rodilla no. Le mandan un paciente que necesita 10 sesiones de pie. y despues le mandan otro paciente de 30 sesiones de mano.

Mario esta disponible en horario matutino.
El horario es configurable por parte del paciente
* Algunos de 7:00 am - 3:00 pm
* Otros de 8:00 am - 2:00 pm
* Otros de 1:00 pm - 7:00 pm

Si Mario está a tope de 7 a 10, pues a ver si se puede de 11 a 2 que sale
Pero que tal que el 29 de septiembre no trabaja, si hay otro terapeuta disponible que hace terapia de mano se asigna.
Aunque si no lo decide el administrador se bloquea la agenda.

Los LTF registran sus dias de vacaciones.
El administrador registra los dias de vacaciones.

Todas las terapias tienen la misma duracion (1Hr).

Hay grupos de Terapias
Un grupo es cuando hay varios pacientes en el mismo horario con un solo LFT.
