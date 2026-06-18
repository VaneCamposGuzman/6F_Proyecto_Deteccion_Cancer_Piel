# 6F_Proyecto_Deteccion_Cancer_Piel
# Sistema de Detección de Lesiones Cutáneas con YOLO

Este proyecto utiliza visión artificial basada en el modelo YOLO para la localización y clasificación de manchas y lesiones en la piel, sirviendo como herramienta de apoyo en el pre-diagnóstico de cáncer de piel.

---

## Caso de Estudio

### A. Problema a resolver
El acceso a médicos dermatólogos especialistas suele ser limitado, costoso o tardado en clínicas de primer contacto o comunidades rurales. Muchas veces, los pacientes ignoran manchas o lunares sospechosos hasta que la enfermedad se encuentra en etapas avanzadas. Este sistema busca reducir la brecha de detección temprana mediante un 'screening' o cribado automatizado, permitiendo al médico general identificar anomalías de manera oportuna y priorizar la canalización urgente de pacientes con riesgo de malignidad.

### B. Descripción del Hardware Propuesto
* **Dispositivo de Captura:** Un dermatoscopio digital médico con luz polarizada y conexión USB/Inalámbrica, acoplado a la computadora o tablet del consultorio.
* **Procesamiento de Datos:** El procesamiento se realiza de forma híbrida en la nube. La imagen capturada se envía mediante una API segura a un servidor web (ej. AWS o Google Cloud) equipado con una GPU dedicada, donde corre el modelo YOLO optimizado para no exigir hardware costoso en la clínica local.
* **Dispositivo de Salida:** Una interfaz web en la pantalla de la computadora del médico general que despliega el reporte visual e indicaciones de urgencia.

### C. Flujo de Funcionamiento del Sistema
1. **Captura:** El médico general atiende al paciente y utiliza el dermatoscopio digital para tomar una fotografía de alta resolución de la lesión cutánea sospechosa.
2. **Procesamiento:** La aplicación del consultorio carga automáticamente la imagen y la envía al modelo YOLO entrenado.
3. **Análisis e Inferencia:** El modelo localiza la mancha mediante un cuadro delimitador (bounding box) y calcula la probabilidad de pertenencia a una categoría (ej. "Benigno" o "Melanoma") en menos de un segundo.
4. **Acción Automatizada:** Si el modelo detecta una lesión con alta probabilidad de malignidad (superior al 70%), el sistema genera una alerta visual roja en la interfaz y **emite una solicitud automática de interconsulta prioritaria** en la agenda del hospital para canalizar al paciente con el dermatólogo especialista en un plazo menor a 7 días. Si es benigno, se archiva en el expediente electrónico para su monitoreo en el chequeo anual.
