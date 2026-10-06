First, let's update your package list and install Python along with `pip` if it isn't already available.

Run the following command to update and install dependencies:

```bash
apt-get update && apt-get install -y python3-pip python3-full
```{{exec}}

Next, install the `pypdf` library, which allows us to programmatically read and write PDF documents:

```bash
pip3 install pypdf --break-system-packages
```{{exec}}
