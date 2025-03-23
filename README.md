<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Juego de Personalidad: Tu Código Personalizado</title>
    <script src="https://unpkg.com/@tailwindcss/browser@4"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        .bg-gradient-to-r {
            background-image: linear-gradient(to right, #ab47bc, #3f51b5); /* Morado a Azul */
        }
        .bg-white {
            background-color: #ffffff;
        }
        .rounded-lg {
            border-radius: 0.75rem; /* 12px */
        }
        .shadow-xl {
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15); /* Sombra más pronunciada */
        }
        .p-8 {
            padding: 2rem; /* 32px */
        }
        .max-w-md {
            max-width: 28rem; /* 448px */
        }
        .w-full {
            width: 100%;
        }
        .text-center {
            text-align: center;
        }
        .text-2xl {
            font-size: 1.5rem; /* 24px */
            line-height: 2rem; /* 32px */
        }
        .font-semibold {
            font-weight: 600;
        }
        .text-indigo-600 {
            color: #4f46e5;
        }
        .mb-6 {
            margin-bottom: 1.5rem; /* 24px */
        }
        .text-gray-700 {
            color: #4b5563;
        }
        .grid {
            display: grid;
        }
        .grid-cols-1 {
            grid-template-columns: repeat(1, minmax(0, 1fr));
        }
        .sm\:grid-cols-2 {
            @media (min-width: 640px) {
                grid-template-columns: repeat(2, minmax(0, 1fr));
            }
        }
        .gap-4 {
            gap: 1rem; /* 16px */
        }
        .mb-4 {
            margin-bottom: 1rem; /* 16px */
        }
        .bg-gradient-to-r {
            background-image: linear-gradient(to right, #f9a8d4, #9c27b0); /* Rosa a Morado */
        }
        .hover\:from-pink-600:hover {
            --tw-gradient-from: #ec4899; /* Rosa más oscuro */
        }
        .hover\:to-purple-600:hover {
            --tw-gradient-to: #7e22ce; /* Morado más oscuro */
        }
        .text-white {
            color: #ffffff;
        }
        .font-semibold {
            font-weight: 600;
        }
        .rounded-full {
            border-radius: 9999px;
        }
        .py-2 {
            padding-top: 0.5rem; /* 8px */
            padding-bottom: 0.5rem; /* 8px */
        }
        .px-4 {
            padding-left: 1rem; /* 16px */
            padding-right: 1rem; /* 16px */
        }
        .transition {
            transition-property: all;
            transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
            transition-duration: 150ms;
        }
        .ease-in-out {
            transition-timing-function: ease-in-out;
        }
        .shadow-md {
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
        }
        .hidden {
            display: none;
        }
        .mt-6 {
            margin-top: 1.5rem; /* 24px */
        }
        .text-xl {
            font-size: 1.25rem; /* 20px */
            line-height: 1.75rem; /* 28px */
        }
        .text-green-600 {
            color: #16a34a;
        }
        .mb-4 {
            margin-bottom: 1rem; /* 16px */
        }
        .text-2xl {
            font-size: 1.5rem; /* 24px */
            line-height: 2rem; /* 32px */
        }
        .font-bold {
            font-weight: 700;
        }
        .text-indigo-700 {
            color: #4338ca;
        }
        .text-gray-600 {
            color: #4b5563;
        }
        .mt-4 {
            margin-top: 1rem; /* 16px */
        }
        .bg-gradient-to-r {
            background-image: linear-gradient(to right, #f43f5e, #f97316); /* Rojo a Naranja */
        }
        .hover\:from-red-500:hover {
            --tw-gradient-from: #c81e1e;
        }
        .hover\:to-orange-500:hover {
             --tw-gradient-to: #c2410c;
        }
        .text-red-500 {
            color: #dc2626;
        }
        .text-sm {
            font-size: 0.875rem; /* 14px */
            line-height: 1.25rem; /* 20px */
        }
        .min-h-screen {
            min-height: 100vh;
        }
        .flex {
            display: flex;
        }
        .justify-center {
            justify-content: center;
        }
        .items-center {
            align-items: center;
        }
        .py-10 {
            padding-top: 2.5rem; /* 40px */
            padding-bottom: 2.5rem; /* 40px */
        }
    </style>
</head>
<body class="bg-gradient-to-r min-h-screen flex justify-center items-center py-10">
    <div class="bg-white rounded-lg shadow-xl p-8 max-w-md w-full text-center">
        <h1 class="text-2xl font-semibold text-indigo-600 mb-6">Descubre tu Código Personalizado</h1>
        <div id="pregunta-container" class="mb-6">
            <p class="text-gray-700">Cargando pregunta...</p>
        </div>
        <div id="opciones-container" class="grid grid-cols-1 sm:grid-cols-2 gap-4 mb-4">
            <button class="bg-gradient-to-r from-pink-500 to-purple-500 hover:from-pink-600 hover:to-purple-600 text-white font-semibold rounded-full py-2 px-4 transition duration-300 ease-in-out shadow-md">Opción 1</button>
            <button class="bg-gradient-to-r from-pink-500 to-purple-500 hover:from-pink-600 hover:to-purple-600 text-white font-semibold rounded-full py-2 px-4 transition duration-300 ease-in-out shadow-md">Opción 2</button>
        </div>
        <button id="siguiente-btn" class="bg-gradient-to-r from-green-400 to-blue-400 hover:from-green-500 hover:to-blue-500 text-white font-semibold rounded-full py-2 px-6 transition duration-300 ease-in-out shadow-lg hidden">Siguiente</button>
        <div id="resultado-container" class="hidden mt-6">
            <h2 class="text-xl font-semibold text-green-600 mb-4">Tu Código Personalizado es:</h2>
            <p id="codigo-personalizado" class="text-2xl font-bold text-indigo-700"></p>
            <p id="descripcion-personalidad" class="text-gray-600 mt-4"></p>
            <button id="reiniciar-btn" class="mt-6 bg-gradient-to-r from-red-400 to-orange-400 hover:from-red-500 hover:to-orange-500 text-white font-semibold rounded-full py-2 px-6 transition duration-300 ease-in-out shadow-md">Reiniciar Test</button>
        </div>
        <div id="mensaje-container" class="text-red-500 text-sm mt-4"></div>
    </div>

    <script>
        const preguntas = [
            {
                pregunta: "¿Qué tipo de proyecto te emociona más crear?",
                opciones: [
                    { texto: "Una aplicación que ayude a la gente a conectar.", codigo: "A" },
                    { texto: "Un videojuego con gráficos impresionantes.", codigo: "B" },
                ],
            },
            {
                pregunta: "¿Cuál de estas habilidades disfrutas más?",
                opciones: [
                    { texto: "Resolver problemas lógicos y complejos.", codigo: "C" },
                    { texto: "Diseñar interfaces de usuario atractivas.", codigo: "D" },
                ],
            },
            {
                pregunta: "¿Cómo prefieres trabajar en un equipo?",
                opciones: [
                    { texto: "Liderando y organizando el trabajo.", codigo: "E" },
                    { texto: "Colaborando y aportando ideas creativas.", codigo: "F" },
                ],
            },
            {
                pregunta: "¿Qué aspecto del desarrollo te interesa más?",
                opciones: [
                    { texto: "La eficiencia y el rendimiento del código.", codigo: "C" },
                    { texto: "La experiencia del usuario y la interactividad.", codigo: "D" },
                ],
            },
            {
                pregunta: "¿Qué entorno de trabajo prefieres?",
                opciones: [
                    { texto: "Uno estructurado con metas claras.", codigo: "A" },
                    { texto: "Uno flexible que permita la experimentación.", codigo: "B" },
                ],
            },
             {
                pregunta: "¿Cuál es tu lenguaje de programación favorito o el que más te gustaría aprender?",
                opciones: [
                    { texto: "Python", codigo: "C" },
                    { texto: "JavaScript", codigo: "D" },
                ],
            },
            {
                pregunta: "¿Qué tipo de desafíos te atraen más?",
                opciones: [
                    { texto: "Desafíos que requieren análisis y lógica.", codigo: "C" },
                    { texto: "Desafíos que permiten la creatividad y la innovación.", codigo: "F" },
                ],
            },
            {
                pregunta: "¿Qué rol te gustaría desempeñar en un proyecto de desarrollo?",
                opciones: [
                    { texto: "Desarrollador Full-Stack.", codigo: "A" },
                    { texto: "Diseñador de Experiencia de Usuario (UX).", codigo: "D" },
                ],
            },
            {
                pregunta: "¿Cómo te describirías mejor?",
                opciones: [
                    { texto: "Organizado y orientado a resultados.", codigo: "E" },
                    { texto: "Creativo y apasionado.", codigo: "F" },
                ],
            },
            {
                pregunta: "¿Qué buscas en un proyecto de tecnología?",
                opciones: [
                    { texto: "La oportunidad de crear algo útil y funcional.", codigo: "A" },
                    { texto: "La oportunidad de crear algo visualmente impactante.", codigo: "B" },
                ],
            }
        ];

        const resultados = {
            "AAAA": {
                titulo: "El Arquitecto",
                descripcion: "Eres una persona organizada, lógica y eficiente. Te gusta construir sistemas sólidos y funcionales. Tu código personalizado refleja tu habilidad para estructurar proyectos y alcanzar metas con precisión."
            },
            "BBBB": {
                titulo: "El Visionario",
                descripcion: "Eres creativo, innovador y te apasiona el diseño. Te gusta explorar nuevas ideas y crear experiencias visualmente impactantes. Tu código personalizado revela tu capacidad para pensar fuera de la caja y crear soluciones originales."
            },
            "CCCC": {
                titulo: "El Analista",
                descripcion: "Eres una persona lógica, analítica y orientada a los detalles. Te gusta resolver problemas complejos y optimizar el rendimiento del código. Tu código personalizado destaca tu habilidad para encontrar soluciones eficientes y precisas."
            },
            "DDDD": {
                titulo: "El Diseñador",
                descripcion: "Eres creativo, intuitivo y te enfocas en la experiencia del usuario. Te gusta crear interfaces atractivas e interactivas. Tu código personalizado refleja tu pasión por el diseño y la usabilidad."
            },
             "EEEE": {
                titulo: "El Líder",
                descripcion: "Eres organizado, eficiente y te gusta tomar la iniciativa. Disfrutas coordinar equipos y alcanzar objetivos. Tu código personalizado refleja tu capacidad de organización y liderazgo."
            },
            "FFFF": {
                titulo: "El Creativo",
                descripcion: "Eres innovador, original y te apasiona la experimentación. Te gusta explorar nuevas ideas y encontrar soluciones únicas. Tu código personalizado revela tu espíritu creativo y tu pasión por la innovación."
            },
            "AAAC": {
                titulo: "El Estratega Eficiente",
                descripcion: "Combinas la planificación con la eficiencia. Te destacas por crear soluciones funcionales y bien estructuradas, optimizando cada detalle para lograr el mejor resultado."
            },
            "AAAD": {
                titulo: "El Arquitecto Creativo",
                descripcion: "Unes la lógica con la creatividad. Diseñas sistemas sólidos con un toque de originalidad, priorizando tanto la funcionalidad como la estética."
            },
            "AACA": {
                titulo: "El Analista Estructurado",
                descripcion: "Eres metódico y preciso en tu análisis. Te enfocas en la lógica y la eficiencia, creando soluciones bien organizadas y fáciles de mantener."
            },
             "AACD": {
                titulo: "El Analista Innovador",
                descripcion: "Combinas el análisis lógico con la creatividad, buscando soluciones eficientes y originales a los problemas."
            },
            "AADA": {
                titulo: "El Diseñador Organizado",
                descripcion: "Aportas estructura y claridad al diseño. Creas interfaces atractivas y funcionales, priorizando la usabilidad y la eficiencia."
            },
            "AADD": {
                titulo: "El Diseñador Visionario",
                descripcion: "Eres un diseñador con visión, capaz de crear experiencias de usuario innovadoras y atractivas, sin perder de vista la funcionalidad."
            },
            "ABAC":{
              titulo: "El Desarrollador Versátil",
              descripcion: "Tienes la capacidad de adaptarte a diferentes aspectos del desarrollo, desde la lógica hasta la creatividad.  Eres capaz de crear proyectos funcionales y atractivos"
            },
            "ABAD":{
                titulo: "El Innovador Práctico",
                descripcion: "Te gusta innovar, pero siempre con un enfoque práctico. Buscas soluciones creativas que sean funcionales y útiles."
            },
            "ABCA":{
                titulo: "El Analista Creativo",
                descripcion: "Eres capaz de analizar problemas complejos y encontrar soluciones creativas y eficientes."
            },
            "ABCD":{
                titulo: "El Creador Integral",
                descripcion: "Posees una combinación única de habilidades que te permiten crear proyectos completos, desde la concepción hasta la implementación y el diseño."
            },
            "ACAD": {
                titulo: "El Desarrollador Lógico",
                descripcion: "Te enfocas en la creación de código eficiente y bien estructurado.  Buscas la optimización y la claridad en cada proyecto."
            },
            "ACBA": {
                titulo: "El Desarrollador Eficiente",
                descripcion: "Priorizas la funcionalidad y la optimización del código.  Te destacas por encontrar soluciones lógicas y eficientes a los desafíos técnicos."
            },
            "ACCA": {
                titulo: "El Programador Analítico",
                descripcion: "Eres hábil para desglosar problemas complejos y crear soluciones de software eficientes y bien estructuradas."
            },
            "ACCD": {
                titulo: "El Ingeniero de Software",
                descripcion: "Diseñas y construyes sistemas de software robustos y eficientes, con un enfoque en la lógica y el rendimiento."
            },
            "ACDA": {
              titulo: "El Diseñador Técnico",
              descripcion: "Tienes un enfoque analítico para el diseño, creando interfaces que no solo son atractivas, sino también funcionales y eficientes."
            },
            "ACDD": {
              titulo: "El Arquitecto de Experiencia",
              descripcion: "Diseñas experiencias de usuario complejas, combinando la lógica del desarrollo con la creatividad del diseño."
            },
            "ADAD":{
                titulo: "El Diseñador Estratega",
                descripcion: "Combinas la creatividad del diseño con el pensamiento estratégico, creando soluciones que cumplen objetivos tanto estéticos como funcionales."
            },
            "ADCA":{
                titulo: "El Desarrollador de Experiencia de Usuario",
                descripcion: "Te enfocas en la creación de experiencias de usuario atractivas y funcionales, con una base sólida en el desarrollo."
            },
            "ADCD":{
              titulo: "El Diseñador Interactivo",
              descripcion: "Creas experiencias de usuario que son a la vez atractivas e interactivas, con un fuerte enfoque en la funcionalidad."
            },
            "BACA": {
                titulo: "El Desarrollador Creativo",
                descripcion: "Combinas la creatividad con la lógica de la programación para desarrollar soluciones innovadoras y atractivas."
            },
            "BACD": {
                titulo: "El Innovador Eficaz",
                descripcion: "Eres capaz de transformar ideas creativas en realidad, con un enfoque en la eficiencia y la funcionalidad."
            },
            "BADA": {
                titulo: "El Diseñador Experimental",
                descripcion: "Te gusta experimentar con nuevas ideas y enfoques en el diseño, buscando siempre la innovación y la originalidad."
            },
            "BADD": {
                titulo: "El Diseñador de Vanguardia",
                descripcion: "Eres un diseñador que siempre está a la vanguardia, explorando nuevas tendencias y creando experiencias de usuario únicas."
            },
            "BBAC": {
                titulo: "El Artista Tecnológico",
                descripcion: "Fusionas el arte y la tecnología para crear proyectos visualmente impactantes y técnicamente sólidos."
            },
            "BBAD": {
                titulo: "El Diseñador Innovador",
                descripcion: "Eres un diseñador que busca constantemente la innovación, creando experiencias de usuario únicas y memorables."
            },
            "BBCA": {
                titulo: "El Desarrollador Apasionado",
                descripcion: "Te apasiona crear proyectos que combinen la creatividad con la funcionalidad, buscando siempre la excelencia en el diseño y el desarrollo."
            },
            "BBCD": {
                titulo: "El Creador de Experiencias",
                descripcion: "Diseñas y desarrollas experiencias de usuario que son a la vez atractivas e interactivas, con un fuerte enfoque en la innovación."
            },
            "BCAD": {
                titulo: "El Desarrollador Imaginativo",
                descripcion: "Utilizas tu imaginación para crear soluciones de software innovadoras y atractivas."
            },
            "BCBA": {
                titulo: "El Programador Creativo",
                descripcion: "Eres un programador que disfruta explorando nuevas formas de resolver problemas, combinando la lógica con la creatividad."
            },
            "BCCA": {
                titulo: "El Artista del Código",
                descripcion: "Ves el código como una forma de arte, creando soluciones elegantes e innovadoras a los desafíos técnicos."
            },
            "BCCD": {
                titulo: "El Arquitecto de la Innovación",
                descripcion: "Diseñas sistemas de software innovadores y creativos, con un enfoque en la experiencia del usuario y la estética."
            },
            "BCDA": {
                titulo: "El Diseñador Experimental",
                descripcion: "Te gusta experimentar con nuevas ideas y enfoques en el diseño, buscando siempre la innovación y la originalidad."
            },
            "BCDD": {
                titulo: "El Pionero del Diseño",
                descripcion: "Eres un diseñador que siempre está a la vanguardia, explorando nuevas tendencias y creando experiencias de usuario únicas."
            },
            "BDAD": {
                titulo: "El Diseñador Visionario",
                descripcion: "Eres un diseñador con una gran visión, capaz de crear experiencias de usuario innovadoras y atractivas."
            },
             "BDCA": {
                titulo: "El Desarrollador Creativo de Interfaces",
                descripcion: "Creas interfaces de usuario que son a la vez funcionales y visualmente atractivas, con un enfoque en la innovación."
            },
            "BDCD": {
                titulo: "El Diseñador de Experiencias Innovadoras",
                descripcion: "Diseñas experiencias de usuario que son únicas y memorables, combinando la creatividad con la funcionalidad."
            },
            "CACA": {
                titulo: "El Analista de Sistemas",
                descripcion: "Te destacas por tu capacidad para analizar y optimizar sistemas, buscando siempre la eficiencia y la precisión."
            },
            "CACD": {
                titulo: "El Analista Creativo de Sistemas",
                descripcion: "Combinas el análisis de sistemas con la creatividad para diseñar soluciones innovadoras y eficientes."
            },
            "CADA": {
                titulo: "El Diseñador de Sistemas Lógico",
                descripcion: "Aplicas la lógica y el análisis al diseño de sistemas, creando soluciones funcionales y bien estructuradas."
            },
            "CADD": {
                 titulo: "El Diseñador de Sistemas Innovador",
                 descripcion: "Diseñas sistemas innovadores que no solo son funcionales, sino también intuitivos y atractivos para el usuario."
            },
            "CBAC": {
                titulo: "El Desarrollador Analítico",
                descripcion: "Eres un desarrollador con una mente analítica, capaz de resolver problemas complejos y crear soluciones eficientes."
            },
            "CBAD": {
                titulo: "El Desarrollador Innovador y Lógico",
                descripcion: "Combinas la lógica del desarrollo con la creatividad para crear soluciones innovadoras y funcionales."
            },
            "CBCA": {
                titulo: "El Programador Analítico",
                descripcion: "Te enfocas en la creación de código eficiente y bien estructurado, con un fuerte énfasis en la lógica y el análisis."
            },
            "CBCD": {
                titulo: "El Ingeniero de Software Creativo",
                descripcion: "Diseñas y construyes sistemas de software innovadores, combinando la lógica de la ingeniería con la creatividad del diseño."
            },
            "CCAD": {
                titulo: "El Desarrollador de Soluciones",
                descripcion: "Te especializas en encontrar soluciones lógicas y eficientes a problemas complejos, utilizando tu habilidad para el análisis y la programación."
            },
            "CCBA": {
                titulo: "El Programador Eficiente",
                descripcion: "Eres un programador que se destaca por su capacidad para escribir código limpio, eficiente y bien estructurado."
            },
            "CCCA": {
                titulo: "El Arquitecto de Software",
                descripcion: "Diseñas la estructura y el funcionamiento de sistemas de software complejos, con un enfoque en la lógica y la eficiencia."
            },
            "CCCD": {
                titulo: "El Ingeniero de Software Senior",
                descripcion: "Lideras el desarrollo de software con un enfoque en la innovación, la eficiencia y la calidad del código."
            },
            "CCDA": {
                titulo: "El Diseñador de Sistemas Analítico",
                descripcion: "Diseñas sistemas complejos con un enfoque en la lógica y la eficiencia, asegurando que sean funcionales y fáciles de mantener."
            },
            "CCDD": {
                titulo: "El Arquitecto de Experiencia de Usuario",
                descripcion: "Diseñas la experiencia del usuario de sistemas complejos, combinando la lógica del desarrollo con la creatividad del diseño."
            },
            "CDAD": {
                titulo: "El Diseñador Lógico de Experiencia",
                descripcion: "Te enfocas en crear experiencias de usuario que sean tanto lógicas como intuitivas, con un fuerte énfasis en la funcionalidad."
            },
            "CDCA": {
                titulo: "El Desarrollador de Sistemas Analítico",
                descripcion: "Diseñas y desarrollas sistemas complejos con un enfoque en la lógica y la eficiencia."
            },
            "CDCD": {
                titulo: "El Diseñador de Experiencia Funcional",
                descripcion: "Creas experiencias de usuario que son a la vez funcionales y atractivas, con un enfoque en la lógica y la claridad."
            },
            "DADA": {
                titulo: "El Diseñador de Experiencia de Usuario",
                descripcion: "Te enfocas en crear experiencias de usuario intuitivas y atractivas, priorizando la estética y la funcionalidad."
            },
            "DADC": {
                titulo: "El Diseñador de Experiencia Creativo",
                descripcion: "Combinas la creatividad con el diseño de experiencia de usuario para crear interfaces innovadoras y atractivas."
            },
            "DACA": {
                titulo: "El Diseñador de Interfaces Lógico",
                descripcion: "Diseñas interfaces de usuario que son tanto atractivas como funcionales, con un fuerte enfoque en la lógica y la claridad."
            },
            "DACD": {
                titulo: "El Diseñador de Interfaces Innovador",
                descripcion: "Creas interfaces de usuario únicas y memorables, combinando la creatividad con la funcionalidad."
            },
            "DBAC": {
                titulo: "El Desarrollador Creativo de Interfaces",
                descripcion: "Diseñas y desarrollas interfaces de usuario que son a la vez atractivas e innovadoras, con un enfoque en la experiencia del usuario."
            },
            "DBAD": {
                titulo: "El Diseñador de Experiencia Innovador",
                descripcion: "Diseñas experiencias de usuario únicas y memorables, combinando la creatividad con la funcionalidad."
            },
            "DBCA": {
                titulo: "El Desarrollador Apasionado de Interfaces",
                descripcion: "Te apasiona crear interfaces de usuario que sean a la vez atractivas y funcionales, con un enfoque en la innovación y la creatividad."
            },
            "DBCD": {
                titulo: "El Creador de Experiencias Digitales",
                descripcion: "Diseñas y desarrollas experiencias de usuario digitales que son a la vez atractivas e interactivas, con un fuerte enfoque en la innovación."
            },
            "DCAD": {
                titulo: "El Diseñador Intuitivo de Interfaces",
                descripcion: "Creas interfaces de usuario que son fáciles de usar y atractivas, con un enfoque en la experiencia del usuario."
            },
            "DCBA": {
                titulo: "El Diseñador de Interfaces Eficiente",
                descripcion: "Diseñas interfaces de usuario que son a la vez funcionales y atractivas, con un enfoque en la eficiencia y la claridad."
            },
            "DCCA": {
                titulo: "El Arquitecto de Interacción",
                descripcion: "Diseñas la estructura y el flujo de interacción de interfaces complejas, con un enfoque en la experiencia del usuario."
            },
            "DCCD": {
                titulo: "El Diseñador de Experiencia de Usuario Senior",
                descripcion: "Lideras el diseño de experiencias de usuario innovadoras y atractivas, con un enfoque en la estrategia y la visión."
            },
            "DCDA": {
                titulo: "El Diseñador de Sistemas Centrado en el Usuario",
                descripcion: "Diseñas sistemas con un enfoque principal en la experiencia del usuario, combinando la funcionalidad con la estética."
            },
            "DCDD": {
                titulo: "El Arquitecto de Experiencia Digital",
                descripcion: "Diseñas experiencias digitales integrales, desde la interfaz hasta la interacción, con un enfoque en la innovación y la creatividad."
            },
            "DDAD": {
                titulo: "El Diseñador de Experiencia Maestro",
                descripcion: "Eres un experto en crear experiencias de usuario que son a la vez intuitivas y memorables, con un enfoque en la excelencia."
            },
            "DDCA": {
                titulo: "El Desarrollador de Experiencia de Usuario Creativo",
                descripcion: "Diseñas y desarrollas experiencias de usuario innovadoras y atractivas."
            },
            "DDCD": {
                titulo: "El Diseñador de Experiencia Excepcional",
                descripcion: "Creas experiencias de usuario que son únicas, memorables y altamente atractivas."
            }
        };

        let respuestas = [];
        let preguntaIndex = 0;

        const preguntaContainer = document.getElementById("pregunta-container");
        const opcionesContainer = document.getElementById("opciones-container");
        const siguienteBtn = document.getElementById("siguiente-btn");
        const resultadoContainer = document.getElementById("resultado-container");
        const codigoPersonalizadoSpan = document.getElementById("codigo-personalizado");
        const descripcionPersonalidadSpan = document.getElementById("descripcion-personalidad");
        const reiniciarBtn = document.getElementById("reiniciar-btn");
        const mensajeContainer = document.getElementById("mensaje-container");

        function cargarPregunta() {
            mensajeContainer.textContent = "";
            const preguntaActual = preguntas[preguntaIndex];
            preguntaContainer.textContent = preguntaActual.pregunta;
            opcionesContainer.innerHTML = "";

            preguntaActual.opciones.forEach((opcion) => {
                const boton = document.createElement("button");
                boton.textContent = opcion.texto;
                boton.className = "bg-gradient-to-r from-pink-500 to-purple-500 hover:from-pink-600 hover:to-purple-600 text-white font-semibold rounded-full py-2 px-4 transition duration-300 ease-in-out shadow-md";
                boton.addEventListener("click", () => seleccionarOpcion(opcion.codigo));
                opcionesContainer.appendChild(boton);
            });
            siguienteBtn.classList.add("hidden");
        }

        function seleccionarOpcion(codigo) {
            respuestas.push(codigo);
            siguienteBtn.classList.remove("hidden");
        }

        function siguientePregunta() {
            if (respuestas.length === preguntas.length) {
                mostrarResultado();
            } else {
                preguntaIndex++;
                cargarPregunta();
            }
        }

        function mostrarResultado() {
            let codigoFinal = respuestas.join("");
             // Asegurar que el código final tenga siempre 4 caracteres.
             if (codigoFinal.length > 4) {
                codigoFinal = codigoFinal.substring(0, 4); // Truncar si es más largo.
             } else if (codigoFinal.length < 4){
                 while (codigoFinal.length < 4) {
                    codigoFinal += "A";
                 }
             }


            const resultado = resultados[codigoFinal] || resultados["DEFAULT"]; //Devuelve un valor por defecto si no lo encuentra
            resultadoContainer.classList.remove("hidden");
            preguntaContainer.classList.add("hidden");
            opcionesContainer.classList.add("hidden");
            siguienteBtn.classList.add("hidden");
            codigoPersonalizadoSpan.textContent = codigoFinal;
            descripcionPersonalidadSpan.textContent = resultado.descripcion;
        }

        function reiniciarTest() {
            respuestas = [];
            preguntaIndex = 0;
            resultadoContainer.classList.add("hidden");
            preguntaContainer.classList.remove("hidden");
            opcionesContainer.classList.remove("hidden");
            cargarPregunta();
        }

        siguienteBtn.addEventListener("click", siguientePregunta);
        reiniciarBtn.addEventListener("click", reiniciarTest);

        cargarPregunta();
    </script>
</body>
</html>
