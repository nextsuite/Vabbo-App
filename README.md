# Vabbo App (escritorio)
App oficial para ordenadores de Vabbo. Permite entrar al cliente flash.

## How to install?
1. Descargar NODE: https://nodejs.org/
 
2. Abre tu terminal o CMD y entra a la carpeta del proyecto.

3. Instala las dependencias con: `npm install`

4. Asegúrate que el archivo `package.json` está correcto.

    • productName = Vabbo
    
    • appId = es.vabbohotel.app (también en Main.js)

5. Abre el archivo de configuración `config.env` e introduce las URL del hotel:

    URL = https://www.habbo.com
    
    SHORT_URL = habbo.com
    
6. Puedes editar `views/home.html`

## Compilar release
7. Abre tu terminal o CMD y pon el comando: `npm start` 

8. La app se abrirá para comprobar que todo está bien, si es así, estás listo para compilar los ejecutables.

9. En el terminal o CMD ejecuta estos comandos para cada sistema:
    * `npm run windows` - para Windows 
    * `npm run mac` - para Mac 
    
10. Si todo ha ido bien, ve a la carpeta `dist` y tendrás los ejecutables .exe / .dmg ahí.


## Firmar la app de mac
1. Busca `package.json`:

		"extraResources": [
			{
				"from": "./plugins/",
				"to": "../plugins"
			}
		],
		
2. Remplaza por:

        "files": "!src/SignHook.js",
        "extraResources": [
            {
                "from": "./plugins/",
                "to": "../plugins"
            }
        ],
        "afterSign": "src/SignHook.js",

3. Abre `src/SignHook.js` y cambia las credenciales por la de tu Apple ID de desarrollador.

        appleId: 'myemail@gmail.com',
        appleIdPassword: '123-321-ab23-m4d',
        
4. Abre tu terminal o CMD y ejecuta: `npm run mac`

Puede tardar unos minutos.
