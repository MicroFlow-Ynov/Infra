This machine will hold all the services in production, so a few conventions can be applied

> No testing container should be put in this VM

# Naming conventions:

Any service name will always be in lower-case
Any service should start either with "server-", "client-" or "bot-"
If it's the main service then just the name of it should comes next
Ex: bot-name
If it's a secondary service (Database ...) then just add a keyword (db-) then the name of the service
Ex: bot-db-name

# Directories

All the bots are in the `bots/` folder
All the others services (Sonar, Nexus...) are in the `services/` folder
Everything related to a homemade website are in the `server/` folder

> All the folder must respect the CamelCase naming convention

# Ports conventions

All the services are managed by a reverse proxy on the hypervisor, so we're kind of free about how we use the ports
By convention:

Bots: 5000-5999
Services: 6000-6999
Websites Clients: 7000-7999
Websites Server and API: 8000 - 8999
Others: 9000-9999

Portainer agent is using the 9001

At the end all the ports will be read from the hypervisor receiving only Https (443)
