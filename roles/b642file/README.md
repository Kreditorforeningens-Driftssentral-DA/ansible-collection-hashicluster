# B642FILE
Basic role for creating local files from a list of base64encoded strings.
Note: Target folder must exist.

## Requirements
N/A

## Role Variables
#### **files** ([])<br>
A list of files to create, with optional properties.
Required for each entry: 'dest' (destination file) and 'data' (base64encoded string)

#### EXAMPLE
```yaml
files:
- dest: /tmp/name1.txt
  data: WWFoYWEhIFlvdSBmb3VuZCBtZSEK
  mode: '0644'
  owner: link
  group: link
- dest: ./name2.txt
  data: WWFoYWEhIFlvdSBmb3VuZCBtZSEK
  mode: '0600'
```

Dependencies
------------
N/A

Example Playbook
----------------
```yaml
---
- hosts: localhost
  connection: local
  become: yes

  collections:
  - 'kred.hashicluster'

  tasks:
  - name: "Include roles"
    include_role:
      name: b642file
    vars:
      files:
      - dest: /tmp/name1.txt
        data: WWFoYWEhIFlvdSBmb3VuZCBtZSEK
        mode: '0644'
      - dest: ./name2.txt
        data: WWFoYWEhIFlvdSBmb3VuZCBtZSEK
        mode: '0644'
...
```
## License
See [LICENSE](https://raw.githubusercontent.com/Kreditorforeningens-Driftssentral-DA/ansible-collection-hashicluster/main/LICENSE)

## Author Information
Rune Rønneseth <rune.ronneseth@kred.no>
