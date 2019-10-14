# AWS ECR Migration

#### Short description
Project used to migrate docker images between cloud and a local machine.

## Prerequisites

#### Local prerequisites
- Docker installed.
- This project installed with:
```bash
pip install aws-ecr-migration
```
or:
```bash
./install.sh
```

#### Cloud prerequisites
- ECR repository created

## Usage

#### Pulling from ECR repository
```python
from aws_ecr_migration.manage import Manager

manager = Manager(
    region='eu-west-1', 
    remote_repository='remote/repository'
)

manager.pull()
```

#### Pushing an image to ECR repository
```python
from aws_ecr_migration.manage import Manager

manager = Manager(
    region='eu-west-1', 
    local_image='myimage',
    remote_repository='remote/repository'
)

manager.push_image()
```

#### Pushing a running container to ECR repository
```python
from aws_ecr_migration.manage import Manager

manager = Manager(
    region='eu-west-1', 
    local_container='mycontainer',
    remote_repository='remote/repository'
)

manager.push_image()
```
