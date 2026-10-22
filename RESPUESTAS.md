# Respuestas

## Fallas del Jenkinsfile

1. El comando de Bruno terminaba con "|| true", entonces la regresion nunca fallaba y el build quedaba en verde aunque las pruebas fallaran.
2. El junit leia los resultados de bruno/smoke en vez de bruno/regresion, entonces Jenkins no mostraba los resultados de la regresion.
3. La imagen se construia antes de correr la regresion, entonces se generaba aunque las pruebas fallaran.

## Builds

- Paso 1, Jenkinsfile corregido: build #1, SHA ee6121d719969757727f08d9d6b0da539cab3726, verde.
- Paso 2, prueba del tope: build #2, SHA b294ba72d14e1226ca7f763078e55f431b091ad6, rojo.
- Paso 3, arreglo de api.py: build #3, SHA 151e92359fdb87a86955f03ed24455ca4ae74b5f, verde.

## Asercion que fallo

res.body.monto eq 60
