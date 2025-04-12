## Dell EMC Unity

## Description
Automate the management of Dell EMC Unity storage systems using Ansible playbooks.

## Installation Instructions

- Docker
- Minikube
- AWX Operator
- Ansible

## Usage
Each folder contains a task file `.yml` to run a specific job. The other files hold the variables or are a Jinja format variable templates to be used. The variables are updated with the values required by the tasks that are run.

Within the directory run the .yml task file.

#Synatax
 ansible-playbook -i <Inventory_Path> <.yml Path>

## Example
root@server:/root/git/Dell-EMC-Unity/Unity/Create-User$ ansible-playbook -i inventory createuser.yml

PLAY [unity] ********************************************************************************************************************************************************************************
TASK [../Auth : Authenticate & retrieve cookie] *********************************************************************************************************************************************
ok: [192.168.1.1]

TASK [../Auth : DEBUG / GOT Login INFO] *****************************************************************************************************************************************************
ok: [192.168.1.1] 

TASK [../Create-User : Authenticate Using Cookies & create user] ****************************************************************************************************************************
ok: [192.168.1.1]

TASK [../Create-User : DEBUG / GOT create_user  INFO] ***************************************************************************************************************************************
ok: [192.168.1.1] => {
    "msg": {
        "ansible_facts": {
            "discovered_interpreter_python": "/usr/bin/python3"
        },
        "cache_control": "no-cache, no-store, max-age=0",
        "changed": false,
        "connection": "close",
        "content": "{\"@base\":\"https://192.168.1.1/api/instances/user\",\"updated\":\"2025-04-12T14:50:23.415Z\",\"links\":[{\"rel\":\"self\",\"href\":\"/user_ansible\"}],\"content\":{\"id\":\"user_ansible\"}}",
        "content_language": "en-US",
        "content_security_policy": "default-src 'self'; font-src 'self' data:; script-src 'self' 'unsafe-eval' 'unsafe-inline'; img-src 'self' data: blob:; style-src 'self' 'unsafe-inline' blob:; frame-ancestors 'self';",
        "content_type": "application/json;version=1.0;charset=UTF-8",
        "cookies": {},
        "cookies_string": "",
        "date": "Sat, 12 Apr 2025 14:50:23 GMT",
        "elapsed": 1,
        "emc_csrf_token": "dummy_csrf_token",
        "expires": "Thu, 01 Jan 1970 00:00:00 GMT",
        "failed": false,
        "json": {
            "@base": "https://192.168.1.1/api/instances/user",
            "content": {
                "id": "user_ansible"
            },
            "links": [
                {
                    "href": "/user_ansible",
                    "rel": "self"
                }
            ],
            "updated": "2025-04-12T14:50:23.415Z"
        },
        "msg": "OK (unknown bytes)",
        "pragma": "no-cache",
        "redirected": false,
        "server": "Apache",
        "status": 201,
        "strict_transport_security": "max-age=63072000; includeSubdomains;",
        "transfer_encoding": "chunked",
        "url": "https://192.168.1.1/api/types/user/instances",
        "warnings": [
            "The value True (type bool) in a string field was converted to 'True' (type string). If this does not look like what you expect, quote the entire value to ensure it does not change.",
            "The value False (type bool) in a string field was converted to 'False' (type string). If this does not look like what you expect, quote the entire value to ensure it does not change."
        ],
        "x_content_type_options": "nosniff",
        "x_frame_options": "SAMEORIGIN"
    }
}

TASK [../Logout : Logout user] **************************************************************************************************************************************************************
ok: [192.168.1.1]

TASK [../Logout : DEBUG / GOT logout  INFO] *************************************************************************************************************************************************
ok: [192.168.1.1] => {

PLAY RECAP **********************************************************************************************************************************************************************************
192.168.1.1             : ok=6    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

root@server:/root/git/Dell-EMC-Unity/Unity/Create-User$


## Contributing
Contributions are welcome! 

## License
This project is licensed under the MIT License - see the LICENSE file for details.


