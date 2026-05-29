# Transpilador de Java (Selenium WebDriver) a JavaScript (Cypress)

## Información del Proyecto
* **Institución:** Universidad Mariano Gálvez de Guatemala 
* **Centro Universitario:** Retalhuleu
* **Facultad:** Ingeniería en Sistemas de Información y Ciencias de la Computación 
* **Ciclo:** Séptimo Ciclo
* **Curso:** Compiladores 
* **Autor:** Mayro Gameros
* **Punteo:** 15 Puntos 

## Descripción General
Este proyecto consiste en un transpilador avanzado diseñado en Java utilizando la herramienta ANTLR4. Su función principal es realizar el análisis léxico y sintáctico de scripts de pruebas automatizadas escritos en un subconjunto de Java con Selenium WebDriver para traducirlos de manera dirigida por sintaxis a código equivalente y funcional en JavaScript para la herramienta Cypress.

## Estructura de Archivos del Proyecto
* `src/Transpilador.g4`: Definición formal de la gramática, tokens y reglas sintácticas.
* `src/GeneradorCypressVisitor.java`: Componente semántico que recorre el AST y mapea las instrucciones hacia Cypress.
* `src/InterfazTranspilador.java`: Aplicación principal (Driver) desarrollada en Java con entorno gráfico (Swing) y manejo de errores en tiempo real.
* `entrada/LoginTest.java`: Archivo de prueba de origen en Java.
* `salida/LoginTest.cy.js`: Archivo físico generado automáticamente por el programa.

## Arquitectura del Compilador
El flujo de procesamiento de datos sigue un patrón clásico de traducción estructurada:

```mermaid
graph TD
    A[Archivo Origen .java] -->|CharStream| B(Lexer: Análisis Léxico)
    B -->|Flujo de Tokens| C(Parser: Análisis Sintáctico)
    C -->|Árbol de Sintaxis Abstracta - AST| D{GeneradorCypressVisitor}
    D -->|Mapeo Semántico de Nodos| E[Archivo Físico Resultante .cy.js]
    
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style E fill:#bbf,stroke:#333,stroke-width:2px
    style D fill:#f96,stroke:#333,stroke-width:2px
