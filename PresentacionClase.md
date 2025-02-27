Hola, Jordi y compis! 

...Estaba pensando que la próxima vez, dependiendo de como ande de tiempo, igual os grabo un vídeo con la presentación del trabajo :P

Hoy quiero mostrar mi proyecto **BrainMorph**, algo en lo que he estado trabajando para clase y que me tiene súper motivado.

### Qué es BrainMorph?
BrainMorph es una plataforma de análisis de imágenes médicas. Comenzamos con imágenes de resonancias, pero la idea es, una vez respondan mi petición de datos ciertas entidades, añadir imágenes PET y DS de problemáticas derivadas de la inflamación y desplazamiento de la masa encefálica. Paro para arrancar, usé tres bases de datos MRI públicas de licencia abierta:  

- Brain Tumor Dataset (MIT)  
- Brain Tumor MRI Dataset (CC0)  
- Brain Tumor Classification (MRI) (MIT)  

La idea es simple pero ambiciosa: armar un buen conjunto de datos desde cero, limpiarlo, ampliarlo sinteticamente y dejarlo listo para que la IA haga magia detectando tumores cerebrales. Aunque queda mucho por pulir, así es como lo he hecho:  

Descargué los DS y me puse a limpiarlas:  
- Comprobé si existían imágenes rotas y me aseguré de que tuvieran al menos 256x256 píxeles de tamaño.  
- Después de buscar en muchos DS, me supuse que muchos procedían de la misma fuente. Así que definí un umbral para quitar duplicados sin perder variedad y eliminar redundancia.  
- Y me he dedicado a aplicar diferentes técnicas de aumento de datos generando 1000 imágenes sintéticas por categoría (*glioma*, *meningioma*, *notumor*, *pituitary*) con modelos propios de *GAN*, *cGAN*, *ProGAN*, *StyleGAN* y *Difusión*. Lo tengo todo en el *Notebook* `EDA.ipynb`.  

Armé un buen registro en `trazabilidad/`  

No me quedé solo en los datos; pensé en cómo esto podría llegar a ser útil de verdad:  
- Un sistema que carga imágenes (tipo DICOM), las limpia, las analiza con redes como *U-Net* y genera datos extra.  
- Detecta tumores, los segmenta, los clasifica y muestra un *dashboard* con mapas de calor para que los médicos lo pillen rápido.  
- Faltaría meterle imágenes *PET*, mejorar los modelos y sacar una interfaz fácil de usar.  
- En “BrainMorph: Revolucionando el Diagnóstico” hablo del problema (pocos datos, diagnósticos lentos) y cómo lo resuelvo con IA y un negocio que podría llegar a $6M en tres años.  

Puse una **Licencia Propietaria** (© 2025 Pedro Ismael Ruiz Larrú). Pueden usarlo para estudiar o probar, pero si alguien quiere cambiarlo o comercializarlo, tiene que hablar conmigo primero. Así protejo mi trabajo.

**BrainMorph** ha comenzado como un ejercicio, pero ahora lo veo como algo que podría ayudar a detectar tumores más rápido. Limpié datos, los hice crecer con IA y dejé todo listo para que esto no se quede en papel. 

A la derecha podeis ver la estructura, y revisar el README y el EDA, donde he realizado y documentado todo el proceso (los modelos grandes no me ha dado tiempo a entrenarlos, pero son 100% funcionales).

¿Qué os parece? ¡Me gustaría saber qué opináis! 

Gracias a tod@s.
