# preprocess-corruption-data

This repository contains the preprocessing of data about corruption in Chile for subsequent use in eventual projects linked to data visualization and communication of information.

This repository does not initially expect any code contributions. However, other forms of support, such as sharing new data sources to include in this project, are welcome.

This project is Open Source, so even if this repository is not expecting code-related Pull Requests, you can create a new project based on this one. For this, it is important to comply with the [GPL-3.0 license](./LICENSE.md). Also, please see the [License Compliance](#license-compliance) section for more details.

## Repository structure

In this repository, you will find the following directories:

- [original_data](./original_data/): Stores the original data from the sources without any modifications.
- [modified_data](./modified_data/): Stores a modified copy of the original data when necessary.
- [preprocessed_data](./preprocessed_data/): Stores the preprocessed data ready for use in the application.
- [data_preprocessing](./data_preprocessing/): Stores the scripts and files used to preprocess the data for the application.

## How to preprocess the data

This repository use [Jupyter Lab](https://jupyter.org/) for the data preprocessing. In the directory [data_preprocessing](./data_preprocessing/) is the Docker Compose configuration and the jupyter notebooks that will be used.

### Running with Docker Compose
It is required to have [Docker and Docker Compose](https://www.docker.com/) installed. This option allows running a container with all the needed dependencies without installing them manually.

1. Start the container: 
Run the following command to start the container: 

```bash
docker compose up 
```

Is important to not run it with detached mode (flag *-d*), because Jupyter Lab runs a local server and will display into the terminal the URL to connect.

2. From the browser go to the URL indicated in the terminal. This will display, the working directory with the following directories:

- [jupyter_notebooks](./data_preprocessing/jupyter_notebooks/)
- [modified_data](./modified_data/)
- [original_data](./original_data/)
- [preprocessed_data](./preprocessed_data/)

With this configuration, the container so then jupyter notebooks will only have access to the files inside this directories. So new files must be inside this directories or extend the configuration inside the [docker compose configuration file](./data_preprocessing/docker-compose.yml) to be accesible.


## Data

This project use the following data sources:

- [Visualizador de datos sobre los casos de corrupción en Chile](https://github.com/bastianolea/corrupcion_chile): GitHub repository of an actual information visualization application about corruption in Chile, created by Bastián Olea Herrera. The data was copy into the directory [corrupcion_chile_bastian_olea](./original_data/corrupcion_chile_bastian_olea/). This application use the [GPL-3.0 license](./LICENSE.md), and as a result, *preprocess-corruption-data* and derivates uses the same license.

- [Base de Datos Estadísticos (BDE) - Banco Central de Chile (BCCh)](https://si3.bcentral.cl/siete): Statistical Database from the Central Bank of Chile. The current data used is the [annual variation of the IPC](https://si3.bcentral.cl/Siete/ES/Siete/Cuadro/CAP_ESTADIST_MACRO/MN_EST_MACRO_IV/PEM_VAR12_IPC_BS23/638421420032988875?cbFechaInicio=1928&cbFechaTermino=2024&cbFrecuencia=MONTHLY&cbCalculo=NONE&cbFechaBase=) (Índice de Precios al Consumidor), consumer's price index, with monthly frecuency. The data was copy into the directory [bde_banco_central](./original_data/bde_banco_central/).


## License Compliance

The data from the [corrupcion_chile](https://github.com/bastianolea/corrupcion_chile) repository is used under the terms of the GPL-3.0 license. The GPL-3.0 license requires that any derivative works also be licensed under the GPL-3.0. Therefore, this project, *preprocess-corruption-data*, is distributed under the GPL-3.0 license. You can find a copy of the GPL-3.0 license in the [LICENSE.md](./LICENSE.md) file in this repository. For more information about the GPL-3.0 license, please visit the [official GPL website](https://www.gnu.org/licenses/gpl-3.0.html).






