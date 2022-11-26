# Phoenix
Run your data science workloads on high-performance cloud infrastructure in the fewest of steps.

# Table of contents
- [CLI Installation](#cli-installation)
- [CLI Usage](#cli-usage)
  - [Running jobs](#running-jobs)
  - [Creating Jupyter Notebooks](#creating-jupyter-notebooks)
- [Agent Setup](#agent-setup)
  - [Prerequisites](#prerequisites)
  - [Install](#install)
  - [Setup](#setup)
- [Contact](#contact)

# CLI Installation

You can download and install the CLI for any of the following platforms.

| Supported Platform | Download (Latest)                |
| -------------------| ---------------------------------|
| Windows            | [Link][cli-latest-windows-amd64] |
| Linux              | [Link][cli-latest-linux-amd64]   |
| macOS              | [Link][cli-latest-macos-amd64]   |

[cli-latest-windows-amd64]: https://github.com/RoboEpics/phoenix-binaries/releases/download/v0.2.0/phx-windows-amd64.exe
[cli-latest-linux-amd64]: https://github.com/RoboEpics/phoenix-binaries/releases/download/v0.2.0/phx-linux-amd64
[cli-latest-macos-amd64]: https://github.com/RoboEpics/phoenix-binaries/releases/download/v0.2.0/phx-darwin-amd64

To download a specific version, visit the [releases page](https://github.com/RoboEpics/phoenix-binaries/releases).

After you downloaded the binary, add executable permission if needed and add it to the executable path of your system.

# CLI Usage

First you need to initialize Phoenix in your data science project directory:

```bash
phx init
```

This will create a `.phoenix` folder inside your project root directory.

Next you need to login to the Phoenix Platform by running this command and filling out your credentials in the prompts:

```bash
phx login
```

As easily as that, now your project is ready for the cloud.

## Running jobs

You can run a job:

```bash
phx run --cluster $CLUSTER_NAME --flavor $FLAVOR_NAME --name $YOUR_JOB_NAME $COMMAND $ARGS
```

## Creating Jupyter Notebooks

You can also run a Jupyter Notebook on-demand and attach it to Google Colab as an external powerful non-interrupting runtime kernel:

```bash
phx jupyter create --cluster $CLUSTER_NAME --flavor $FLAVOR_NAME --name $YOUR_JUPYTER_INSTANCE_NAME
phx jupyter attach
```

Now, as long as your terminal is open, you can connect your Colab to this runtime using the "Connect to a local runtime" button in Colab interface.

You can read more about how to connect Colab to a local runtime [here](https://research.google.com/colaboratory/local-runtimes.html).

# Agent Setup
If you want to be a compute resource provider, you can install the Agent on your machine and connect it to the Compute Marketplace.

## Prerequisites

- Docker
- A user who has access to the Docker engine (e.g. has the `docker` group)
- Graphics Driver for your hardware and platform ([NVIDIA](https://www.nvidia.com/download/index.aspx) or [AMD](https://www.amd.com/en/support))

**Note: The Agent does not need to be run with `sudo` privileges.**

## Install

Download the Agent for your platform:

| Supported Platform | Download (Latest)                  |
| -------------------| -----------------------------------|
| Windows            | [Link][agent-latest-windows-amd64] |
| Linux              | [Link][agent-latest-linux-amd64]   |
| macOS              | [Link][agent-latest-macos-amd64]   |

[agent-latest-windows-amd64]: https://github.com/RoboEpics/phoenix-binaries/releases/download/agent-v0.1.0-alpha/agent-windows-amd64.exe
[agent-latest-linux-amd64]: https://github.com/RoboEpics/phoenix-binaries/releases/download/agent-v0.1.0-alpha/agent-linux-amd64
[agent-latest-macos-amd64]: https://github.com/RoboEpics/phoenix-binaries/releases/download/agent-v0.1.0-alpha/agent-darwin-amd64

After you downloaded the binary, rename the binary to `agent`, add executable permission if needed and add it to the executable path of your system.

## Setup

Run the `connect` subcommand of the Agent in a persistant terminal session (e.g. `tmux`):

```bash
./agent connect <NODE-NAME> <API-ADDRESS> [<GATEWAY-ADDRESS>]
```

You should see three logs showing that the Agent is connected to the different API resources. As long as the Agent is running, your machine is connected to the marketplace and users can use the compute resource to run their workloads.

# Contact
If you had any questions or problems, join our server on [**Discord**](https://discord.gg/8DMfjmn6gc).
