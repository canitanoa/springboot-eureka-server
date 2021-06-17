# springboot-eureka-server
## Servidor Eureka

Servidor para el registro y localización de microservicios, balanceo de carga y tolerancia a fallos. 
Su función es registrar las diferentes instancias de microservicios existentes, su localización, estado y metadatos.

> Como funciona?:
- Cada microservicio, durante su arranque, se comunicará con el servidor Eureka para notificar que está disponible, dónde está situado, sus metadatos… 
- De esta forma Eureka mantendrá en su registro la información de todos los microservicios del ecosistema.
- El nuevo microservicio continuará notificando a Eureka su estado cada 30 segundos, lo que denominan ‘heartbeats’. 
- Si después de tres periodos Eureka no recibe notificación de dicho microservicio, lo eliminará del registro. 
- De la misma forma una vez vueltos a recibir tres notificaciones considerará el servicio disponible de nuevo.
- Cada cliente de Eureka podrá también recuperar el registro para localizar otros microservicios con los que necesite comunicarse. 
- Dicha información de registro se cachea en el cliente.


> Que aporta?:
- Abstracción de la localización física de los microservicios: cualquier microservicio que sea un cliente Eureka solo necesita conocer el identificador del microservicio al que desea invocar y Eureka resolverá su localización, puerto
- Conocer el estado de nuestro ecosistema de microservicios: Eureka proporciona un dashboard que permite ver los microservicios existentes actualmente en el registro.
- Eureka fue inicialmente desarrollado por Netflix, quien utiliza AWS como IaaS, así Eureka fue diseñado para integrarse fácilmente con los servicios de Amazon.
- Eureka se integra con Asgard para la realización de despliegues haciendo más sencillo el cambio a nuevas o viejas releases.
