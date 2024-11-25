# 01. How is modeled a network in PowSyBl ?

Rougly speaking, a network in PowSyBl is modeled by a **set of objects** that represent the **different components of the real network**. These objects are interconnected to each other to represent the physical connections between the components. There are coded in some different classes that are part of the PowSyBl library.

## What are the main component of a real network ?

Before diving into the modeling of a network in PowSyBl, let's first understand what are the main components of a real network. A network is composed of several elements that are interconnected to each other. The main components of a network are:

<br>
<details>
<summary><b>DC Line</b></summary>
<br>

*A DC line is a transmission line that carries direct current (**DC**) electricity at high voltage. Since the current war (end of the 19th century), the network is mainly composed of AC lines. However, DC lines are becoming more and more popular because they are more efficient for long-distance transmission (reducing the losses), connecting asynchronous grids or offshore wind farms to the main grid.*

<br>
</details>


<details>
<summary><b>AC Line</b></summary>
<br>

*An AC line is a transmission line that carries alternating current (**AC**) electricity at high voltage.*

<br>
</details>

<details>
<summary><b>Tie Line</b></summary>
<br>

*A tie line is a transmission line that connects two different areas of the network. It is used to exchange power between these two areas. In reality, a tie line can be an AC line or a DC line depending on the distance between the two areas. Nonetheless, in PowSyBl, a tie line is always represented as an AC line otherwise we would talk about a "**HVDC Line**" (**H**igh **V**oltage **D**irect **C**urrent **L**ine). Moreover, even if in real life, we mainly talk about a tie line to exchange electricity between two countries, in PowSyBl, a tie line can be used to exchange power between two bidding zones.*

<br>
</details>

<details>
<summary><b>Transformer</b></summary>
<br>

*A transformer is a ***static electrical device*** that transfers electrical energy between two or more circuits through electromagnetic induction. A varying current in ***one coil of the transformer produces a varying magnetic flux***, which, in turn, induces a varying electromotive force across a second coil wound around the same core. This way, transformers are used to increase or decrease the voltage of an AC line. In  pywposybl, a transformer may either be **2 windings** or **3 windings**.*

<br>
</details>  

<details>
<summary><b>Busbar</b></summary>
<br>

*A busbar is a metallic strip or bar, typically housed inside switchgear, panel boards, and busway enclosures for local high current power distribution. In PowSyBl, a busbar is used to represent a connection point in the network where several components are connected to each other.*

<br>
</details>

<details>
<summary><b>Breaker</b></summary>
<br>

*A circuit breaker is an automatically operated electrical switch designed to protect an electrical circuit from damage caused by an overload or a short circuit. In PowSyBl, a breaker is used to represent a switch that can be opened or closed to connect or disconnect two components in the network. In real life, a breaker can be opened or closed both manually or automatically under load conditions.*

<br>
</details>

<details>
<summary><b>Disconnector/Switch</b></summary>
<br>

*A disconnector is an electrical switch that is used to isolate a part of the network. In PowSyBl, a disconnector is used to represent a switch that can be opened or closed to isolate a part of the network. The main difference between a breaker and a disconnector is that a disconnector is not designed to be opened or closed under load conditions since there would be a risk of creating an electric arc. Indeed, while a breaker is designed to interrupt significant currents and positioned upstream to protect a section of the network, a disconnector is positioned alongside the breaker and is used to isolate the section of the network that is protected by the braker (for maintenance purposes for example).*

<br>
</details>

<details>
<summary><b>Generator</b></summary>
<br>

*A generator is a device that converts mechanical energy into electrical energy. In PowSyBl, a generator is used to represent a power plant that produces electricity. A generator is connected to the network through a transformer and a breaker.*

<br>
</details>

<details>
<summary><b>Load</b></summary>
<br>

*A load is an electrical device that consumes electrical energy. In PowSyBl, a load is used to represent a consumer that consumes electricity. A load is connected to the network through a breaker. Please note that the difference between a load and a generator in pypowsybl is really related to the direction of the power flow. A generator produces electricity and injects it into the network while a load consumes electricity from the network.*

<br>
</details>

<details>
<summary><b>Shunt compensators</b></summary>
<br>

*A shunt is a device that is used to regulate the voltage in the network. In PowSyBl, a shunt is used to represent a device that can be connected or disconnected to the network to regulate the voltage. A shunt is connected to the network through a breaker.*

<br>
</details>

<details>
<summary><b>Battery</b></summary>
<br>

*A battery is a device that stores electrical energy. In PowSyBl, a battery is used to represent a device that can store electricity. A battery is connected to the network through a transformer and a breaker.*

<br>
</details>

<details>
<summary><b>Dangling Line</b></summary>
<br>

*A dangling line is a line that ***is not connected to any other component in the network***.This can be useful to represent a line that is not yet connected to the network or a line that has been disconnected from the network. It is quite common to use two dangling lines to represent a tie line since two ***TSOs may manage differently the same tie line***.*

<br>
</details>

<details>
<summary><b>Area</b></summary>
<br>

*An area is a theorical part of the network that is ***connected to the rest of the network through tie lines***. In PowSyBl, an area is used to represent a part of the network that is connected to the rest of the network through tie lines. An area is connected to the network through a breaker.*

<br>
</details>

<details>
<summary><b>Static Var compensators</b></summary>
<br>

*A static var compensator is a device that is used to regulate the reactive power in the network. In PowSyBl, a static var compensator is used to represent a device that can be connected or disconnected to the network to regulate the reactive power.*

</details>

## How is modeled a network in PowSyBl ?

> [!NOTE]
>There are two ways to model a network topology in PowSyBl:
>
>- The **Node-Breaker** model
>- The **Bus Branch** model

<details>
<summary><b>The Node-Breaker model</b></summary>

#### Detail level

The **Node-Breaker** model is the most common way to model a network, generally speaking. The node-breaker topology provides a **granular representation of the network**, including **every individual component** such as circuit **breakers**, **switches**, and **physical connectors**. Each node corresponds to a physical or electrical connection point.

#### Usage

This method is suitable for detailed studies such as network configuration analysis and simulating the impact of a specific component failure or opening/closing a breaker.

</details>
<br>
<details>
<summary><b>The Bus Branch model</b></summary>
<br>

#### Detail level

The **Bus Branch** model is an alternative way to model a network. The bus-branch topology is a **simplified abstraction**. Electrical substations are represented as "**buses**" and transmission lines or transformers as **branches** connecting these **buses**.

#### Usage

This approach is used for broader analyses such as **power flow studies**, **long-term planning** or **simplified short-circuit calculations**.

</details>

### Comparison

| **Feature**           | Node-Breaker                          | Bus-Branch                        |
|-------------------|---------------------------------------|-----------------------------------|
| **Level of detail**   | Highly detailed                       | Simplified                        |
| **Elements modeled**  | Circuit breakers, switches            | Buses and branches (lines)        |
| **Main applications** | Switching studies, faults             | Power flow, planning              |
| **Complexity**        | High                                  | Low                               |
| **Simulation time**   | Long                                  | Short                             |


### Diving into the code

In PowSyBl, there is actually one class representing the network namely the `Network` class. Nonetheless this class contains as many attributes as the number of components as we have seen above. Each attribute is a dataframe that you can get or set to model the network using the getters and setters of the `Network` class. To know more about the `Network` class, you can check the [official documentation](https://powsybl.readthedocs.io/projects/pypowsybl/en/stable/reference/network.html).


<details><summary><b>All elements</b></summary>

> [!TIP]
>Here is the list of all the elements that can be modeled in PyPowSyBl:
>
>
>- areas
>- buses (from bus view)
>- buses from bus/breaker view
>- lines
>- 2 windings transformers
>- 3 windings transformers
>- generators
>- loads
>- shunt compensators
>- dangling lines
>- LCC and VSC converters stations
>- static var compensators
>- switches
>- voltage levels
>- substations
>- busbar sections
>- HVDC lines
>- ratio and phase tap changer steps associated to a 2 windings transformers
>- identifiables that are all the equipment on the network
>- injections
>- branches (lines and two windings transformers)
>- terminals are a practical view of those objects which are very important in the java implementation

</details>


> ## Now let's see how to create a network by hand from scratch...