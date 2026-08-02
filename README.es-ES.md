

Hola, lamento no estar manteniendo esta biblioteca desde hace bastante tiempo. Puedes consultar un nuevo fork de esta en https://github.com/jpudysz/react-native-turbo-mock-location-detector, parece que se mantiene regularmente. Gracias a https://github.com/jpudysz

## Detector de ubicación simulada de React Native / Detector de apps de suplantación de ubicación

⚠️ Un fork de [react-native-mock-location-detector](https://github.com/adkandari/react-native-mock-location-detector) pero con correcciones.

Si estás desarrollando una aplicación basada en ubicación en RN, debes validar si el usuario está utilizando aplicaciones de suplantación de ubicación o no. Esta biblioteca no permite al usuario usar la app si hay alguna aplicación de ubicación simulada activa en el dispositivo.

![Image description](https://i.imgur.com/iT7OpSs.gif)

## Primeros pasos

`$ npm install react-native-detect-mock-location --save`

### Instalación mayormente automática

`$ react-native link react-native-detect-mock-location`

### Instalación manual

#### Android

1. Abre `android/app/src/main/java/[...]/MainActivity.java`

- Agrega `import com.mocklocation.reactnative.RNMockLocationDetectorPackage;` a las importaciones en la parte superior del archivo

- Agrega `new RNMockLocationDetectorPackage()` a la lista devuelta por el método `getPackages()`

2. Agrega las siguientes líneas a `android/settings.gradle`:

```

include ':react-native-mock-location-detector'

project(':react-native-mock-location-detector').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-mock-location-detector/android')

```

3. Inserta las siguientes líneas dentro del bloque de dependencias en `android/app/build.gradle`:

```

implementation project(':react-native-mock-location-detector')

```

## Uso

1. Asegúrate de que tu aplicación tenga el permiso de ubicación antes de llamar a esta función.

2. Argumentos de la función checkMockLocationProvider: Título del cuadro de diálogo, Texto del cuadro de diálogo, Texto del botón del cuadro de diálogo

```javascript
import RNMockLocationDetector from "react-native-detect-mock-location";

const isLocationMocked: boolean =
  await RNMockLocationDetector.checkMockLocationProvider();

if (isLocationMocked) {
  // La ubicación está simulada o suplantada

  return;
}

// La ubicación es correcta
```
