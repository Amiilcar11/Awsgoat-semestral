# Control defensivo: AWS Config

Metodo de grabacion

![Evidencia img_088.png](screenshots/img_088.png)

Definimos el método de grabación del servicio. Se seleccionó la estrategia "Todos los tipos de recursos con anulaciones personalizables", la cual permite que AWS Config registre todos los tipos de recursos actuales y futuros admitidos en la región, incluyendo la posibilidad de anular la frecuencia de registro o excluir tipos de recursos específicos.

Reglas administradas por AWS

![Evidencia img_089.png](screenshots/img_089.png)

Esta regla, de tipo "CHANGE-TRIGGERED", verifica que la versión predeterminada de las políticas de AWS Identity and Access Management (IAM) no otorgue acceso de administrador; es decir, evalúa como no conforme cualquier política que contenga una declaración

Creacion de regla

![Evidencia img_090.png](screenshots/img_090.png)

Una vez ya hayamos creado, ya habremos completado este paso, lo que se busca con esta regla es detectar la creación de políticas IAM excesivamente permisivas
