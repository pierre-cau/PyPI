<p align="center">
    <img src="assets/img/logo_lfe_powsybl.svg" alt="PowSyBl Logo" width="200"/>
</p>



<h1 align="center">PyPowSyBl for beginners 🚀</h1>

[![PyPI Latest Release](https://img.shields.io/pypi/v/pypowsybl.svg)](https://pypi.org/project/pypowsybl/)
[![Documentation Status](https://readthedocs.org/projects/pypowsybl/badge/?version=latest)](https://pypowsybl.readthedocs.io/en/latest/?badge=latest)
[![Slack](https://img.shields.io/badge/slack-powsybl-blueviolet.svg?logo=slack)](https://join.slack.com/t/powsybl/shared_invite/zt-rzvbuzjk-nxi0boim1RKPS5PjieI0rA)
____

Python code quality :
[![Quality Gate Status (python)](https://sonarcloud.io/api/project_badges/measure?project=powsybl_pypowsybl&metric=alert_status)](https://sonarcloud.io/dashboard?id=powsybl_pypowsybl)
[![Coverage](https://sonarcloud.io/api/project_badges/measure?project=powsybl_pypowsybl&metric=coverage)](https://sonarcloud.io/dashboard?id=powsybl_pypowsybl)

___

## Table of contents

- [Introduction](#introduction)
- [Installation](#installation)
- [License](#license)
- [Author](#author)



## Introduction

#### This repository is a tutorial for really beginners who want to learn how to use PowSyBl library in Python.

<div background-color="lightblue">
    <h4 align="center">Used by...
    <p align="center">
        <img src="assets/img/RTE_Logotype_externe_RVB_Bleu.png" alt="RTE Logo" height="80" padding=10/>
        <img src="assets/img/logo-coreso-pos.png" alt="CORESO Logo" height="80" padding=10/>
    </p>
</div>

### But what is PowSyBl?

PowSyBl is an **open-source and powerful library** for modeling and analyzing **electrical networks**. Developed by **RTE**, the **French Transmission System Operator**. It stands for **Power System Blocks**.
Initially a **Java library**  for modeling and analyzing electrical networks, it has been extended to **Python** with the **PyPowSyBl** library.

The library aims both to be an **instrument for research and development** in the field of electrical networks and **an operational tool**. It is **daily used to study the impact of different scenarios** on the electrical grid, such as the addition of **new generation units**, the connection of **new consumers**, or the **failure of existing equipment** to ensure the stability of the electrical grid, the security of its operation, and the reliability of its components.

### Growing Interest in PowSyBl

> [!NOTE]
> In recent years, the enthusiasm around **PowSyBl** has grown significantly. It is now not only used industrially by RTE but also by **new academic players**, other Transmission System Operators (**TSOs**), and even **Regional Coordination Centers** like **CORESO**. Learning to use such a library is therefore **very instructive** on a personal level for understanding how to model the behavior of an electrical network, and it also provides a **real added value for working** in this field.

### What will you learn in this tutorial?


#### In this tutorial, we will cover really the bascis of PyPI namely:

- [] 📊 01 *How is modeled a network in PowSyBl*
- [] 🛠️ 02 *How to create a network by hand from scratch*
- [] 📁 03 *How to import an existing network from a file*
- [] ⚡ 04 *How to run a load flow analysis*
- [x] 👀 05 *How to visualize a network*
- [] 💾 06 *How to export a network to a file*



> [!TIP]
> Please note that **PyPI** and **PowSyBl** are **very powerful tools** for ensuring the security of the electrical grid and its operation. **I plan to write a more advanced tutorial for `PyPI` in the future and also one for the Java library**. Nonetheless, if you are eager to learn more about PyPI, its full documentation made with Sphinx can be found [here](https://powsybl.readthedocs.io/projects/pypowsybl/en/stable/). This documentation is very well written and lets you know a wide range of possibilities that you can achieve with PyPI.



## Installation 

To use this tutorial, please ensure python is installed on your machine. You can download it from [here](https://www.python.org/downloads/). 
PyPowSyBl (shorten as `PyPI`) requires `Python 3.8` to `Python 3.12`. `PyPI` can be easily installed using `pip` which is the package installer for Python on **Linux**, **macOS**, and **Windows**.

If you don't have `pip` installed, you can install it by running the following command:

```bash
python get-pip.py
```

Once done, you can upgrade `pip` by running the following command: 

```bash
pip install --upgrade setuptools pip
```

Then, you can install all the required packages by running the following command:

```bash
pip install -r requirements.txt
```

If you want to install specifically `PyPI`, you can run the following command:

```bash
pip install pypowsybl
```


>[!TIP]
>If you are using a **virtual environment**, you can create one by running the following command:
>
>```bash
>python -m venv venv
>```
>
>Then, you can activate the virtual environment by running >the following command:
>
>```bash
>source venv/bin/activate
>```
>
>Once done, you can install all the required packages.


## License 

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

> [!WARNING]
> Please note that PyPowSyBl is under an MPL 2.0 license. Please refer to the [official documentation](https://powsybl.readthedocs.io/projects/pypowsybl/en/stable/) for more information.

## Author

- [**Pierre CAU**](mailto:pcaupro@gmail.com) 


___

## Copyright

&copy; 2024 RTE. All rights reserved.

