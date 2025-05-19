
# Icono y Splash Screen para app
Para generar tanto el Icono como el Splash Screen se usó como guía la página web de Capacitor, la cuál presenta una guía rápida de cómo generar estos elementos.

Para instalar la carpeta de archivos:
npm install @capacitor/assets

Estructura estricta de los archivos:

    assets/
        ├── icon-only.png
        ├── icon-foreground.png
        ├── icon-background.png
        ├── splash.png
        └── splash-dark.png

Para los íconos, es indispensable que tengan una resolución de 1024 x 1024 px
Para el splash, 2732 x 2732

Posterior a ello se instala la dependencia de splash screen en el proyecto con el comando: 
#### npm install @capacitor/splash-screen

Y la configuracion en el archivo capacitor.config.ts:

    plugins:{
        SplashScreen: {
            launchShowDuration: 0,
            launchAutoHide: true,
            backgroundColor: "#000000",
            androidSplashResourceName: "splash",
            androidScaleType: "CENTER_CROP",
            showSpinner: false,
            androidSpinnerStyle: "large",
            iosSpinnerStyle: "small",
            spinnerColor: "#999999",
            splashFullScreen: false,
            splashImmersive: false,
            layoutName: "launch_screen",
            useDialog: false,
        }
    }


Ahora configuramos el archivo app.component.ts para mostrar el Splash:

    import { SplashScreen } from '@capacitor/splash-screen'; <-- Importa la librería
        
        <--otras configuraciones-->

        export class AppComponent {
        constructor() {this.showSplash()}

        async showSplash() {
         await SplashScreen.show({
            autoHide: true,
            showDuration: 3000
            });
        }
    }


Ya con todo preparado, generamos los assests para el splash con el comando:

#### npx capacitor-assets generate

Como último paso, sincronizar los cambios con el plugin de android y abrir Android Studio, revisar el Manifest con los permisos adecuados (cámara y almacenamiento) y realizar el deploy de la aplicación

### Deploy en dispositivo Android






# Icono y Splash Screen para app
Para generar tanto el Icono como el Splash Screen se usó como guía la página web de Capacitor, la cuál presenta una guía rápida de cómo generar estos elementos.

Para instalar la carpeta de archivos:
npm install @capacitor/assets

Estructura estricta de los archivos:

    assets/
        ├── icon-only.png
        ├── icon-foreground.png
        ├── icon-background.png
        ├── splash.png
        └── splash-dark.png

Para los íconos, es indispensable que tengan una resolución de 1024 x 1024 px
Para el splash, 2732 x 2732

Posterior a ello se instala la dependencia de splash screen en el proyecto con el comando: 
#### npm install @capacitor/splash-screen

Y la configuracion en el archivo capacitor.config.ts:

    plugins:{
        SplashScreen: {
            launchShowDuration: 0,
            launchAutoHide: true,
            backgroundColor: "#000000",
            androidSplashResourceName: "splash",
            androidScaleType: "CENTER_CROP",
            showSpinner: false,
            androidSpinnerStyle: "large",
            iosSpinnerStyle: "small",
            spinnerColor: "#999999",
            splashFullScreen: false,
            splashImmersive: false,
            layoutName: "launch_screen",
            useDialog: false,
        }
    }


Ahora configuramos el archivo app.component.ts para mostrar el Splash:

    import { SplashScreen } from '@capacitor/splash-screen'; <-- Importa la librería
        
        <--otras configuraciones-->

        export class AppComponent {
        constructor() {this.showSplash()}

        async showSplash() {
         await SplashScreen.show({
            autoHide: true,
            showDuration: 3000
            });
        }
    }


Ya con todo preparado, generamos los assests para el splash con el comando:

#### npx capacitor-assets generate

Como último paso, sincronizar los cambios con el plugin de android y abrir Android Studio, revisar el Manifest con los permisos adecuados (cámara y almacenamiento) y realizar el deploy de la aplicación

### Deploy en dispositivo Android





![image](https://github.com/user-attachments/assets/043423e1-da5f-4b7a-8fe1-20e4b7339484)
![image](https://github.com/user-attachments/assets/01d4715d-714b-4ddd-9b1d-9c2de0555585)






