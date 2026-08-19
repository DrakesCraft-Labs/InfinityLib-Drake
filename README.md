<p align="center"><img src="https://raw.githubusercontent.com/DrakesCraft-Labs/InfinityLib-Drake/main/banner.svg" alt="InfinityLib-Drake" width="100%"></p>

# InfinityLib-Drake

> ### 🏰 ¡Únete a la Comunidad Oficial de DrakesCraft!
> 
> * 🎮 **IP del Servidor**: `play.drakescraft.net` *(Java 1.21.11 & Bedrock)*
> * 💬 **Discord Oficial**: [discord.gg/drakescraft](https://discord.gg/rR7FbfCt9Y)
> * 🌐 **Web & Guía**: [drakescraft.net](https://drakescraft.net) — 🛒 **Tienda**: [tienda.drakescraft.net](https://tienda.drakescraft.net)
> 
> *¡Juega con este addon y más de 80 expansiones optimizadas en vivo en nuestra network de supervivencia técnica!*

---

Adaptación de [InfinityLib](https://github.com/Mooy1/InfinityLib) al core Slimefun de
**DrakesCraft** (Paper/Purpur 1.21.11, Java 21).

**No es un plugin.** Es una librería: se empaqueta dentro de los addons que la usan.

## Por qué existe

InfinityLib es un framework para escribir addons de Slimefun — clase base del plugin, máquinas
con su GUI, tipos de receta, grupos y subgrupos, tareas, constructores de items. Está compilada
contra `io.github.thebusybiscuit`, y el core de DrakesCraft repaquetó Slimefun a
`com.github.drakescraft_labs`, así que la original no resuelve ni una clase aquí.

Tres addons de la cosecha dependen de ella:

| Addon | Ficheros que la usan | Estado |
|---|---|---|
| [ObsidianExpansion](https://github.com/DrakesCraft-Labs/ObsidianExpansion) | 10 | portado y en producción |
| SlimefunWarfare | 13 | pendiente |
| MagicXpansion | 2 | pendiente |

Reescribir el framework en cada uno no tenía sentido. Portar la librería una vez los desbloquea
a los tres — y los dos pendientes son de los más pesados de la lista.

## Qué cambiamos

Nada de diseño. Solo lo que hace falta para que compile y funcione aquí:

- Paquetes de Slimefun al core Drake, incluido el árbol legacy de `me.mrCookieSlime` y dough,
  que el core relocaliza a `com.github.drakescraft_labs.slimefun4.libraries.dough`.
- Java 21 y `paper-api` 1.21.11, en vez de Java 8 y Paper 1.17.
- `maven-shade-plugin` a 3.6.1: por debajo de 3.5 no sabe leer bytecode de Java 21 y falla al
  empaquetar con `IllegalArgumentException: Unsupported class file major version 65`.
- La versión pasa a `1.3.10-Drake-1.21.11`, para que no se confunda con la 1.3.10 de upstream si
  ambas acaban en el mismo repositorio local de Maven.

Los nombres de paquete y de clase de la librería **se dejan intactos**, para que las
actualizaciones de arriba sigan siendo legibles y los addons que la usan no necesiten cambios.

## Uso

```xml
<dependency>
    <groupId>io.github.mooy1</groupId>
    <artifactId>InfinityLib</artifactId>
    <version>1.3.10-Drake-1.21.11</version>
</dependency>
```

Se empaqueta dentro del addon con el shade, como la original.

## Crédito

El trabajo de fondo es de **Mooy1**. Licencia **GPL-3.0**, conservada sin modificar. Los detalles
están en [UPSTREAM.md](UPSTREAM.md).

## ⚖️ Upstream Attribution & License / Licencia y Créditos

- **Original Project / Upstream**: Slimefun4 Community Addon.
- **Port & Maintenance**: DrakesCraft Labs team (Compatibility for Paper / Purpur 1.21.11).
- **License**: GPL-3.0 / MIT.
- **Source Code**: [GitHub Repository](https://github.com/DrakesCraft-Labs/InfinityLib-Drake)
- **Support & Issues**: [GitHub Issues](https://github.com/DrakesCraft-Labs/InfinityLib-Drake/issues) | [Discord](https://discord.gg/rR7FbfCt9Y)

*This project is an open-source derivative work maintained by DrakesCraft Labs under the terms of its original license. All original assets and concepts belong to their respective creators.*
