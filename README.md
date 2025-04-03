
# Discover contiguous network inventory

Discover all types of connected network equipment using CDP neighbor information.

## Installation

Install package using pip

```bash
  pip install cisco_discovery
```
## Run Locally

Clone the project

```bash
  git clone https://github.com/tkdebnath/cisco_discovery.git
```

Go to the project directory

```bash
  cd cisco_discovery
```

Install dependencies

```bash
  pip install -r requirements.txt
```


## Environment Variables

To run this project, you will need to add the following environment variables to your .env file

`NETMIKO_USERNAME="<username>"`

`NETMIKO_PASSWORD="<password>"`


## Usage/Examples

```python
from cisco_discovery import runner

if __name__=='__main__':
    
    host = input("Enter any IP of cisco router or switch")
    
    # preference of passed username and password argument is higher than env variable
    obj_discovery = runner(host=host, threads=10, username="username", password="password", env=".env")
    
    """
    default value for directory= "output" 
    default value for file_name= datetime.now().strftime(r"%d_%m_%Y__%I-%M_%p")
    """
    # Generate CSV file for nodes and edges
    obj_discovery.to_csv_nodes(directory="output", file_name= "file_name")
    obj_discovery.to_csv_edges(directory="output", file_name= "file_name")
    
    # Generate Excel file for nodes and edges
    obj_discovery.to_excel_nodes(directory="output", file_name= "file_name")
    obj_discovery.to_excel_edges(directory="output", file_name= "file_name")
    
    # Generate CSV for nodes and edges at once
    obj_discovery.to_csv(directory="output", file_name= "file_name")
    
    # Generate CSV for nodes and edges at once
    obj_discovery.to_excel(directory="output", file_name= "file_name")
```


## Authors

- [@tkdebnath](https://github.com/tkdebnath/)
