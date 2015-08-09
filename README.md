# REST API client for Tuleap open ALM

The purpose of this project is to create a python module that can be used for accessing a Tuleap
instance using its REST API.

## Usage example:
```python
from Tuleap.RestClient.Connection import Connection
from Tuleap.RestClient.Projects import Projects

connection = Connection()
success = connection.Login("https://tuleap.example.com:443/api",
                           "username",
                           "password") 

if success:
    projects = ProjectList(connection)
    
    success = projects.Request()
    
    if success:
        projectList = projects.GetData()

connection.Logout()
```