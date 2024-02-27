# Use envrion
## Django
in setting.py | views.py load dotenv

    import os
    from dotenv import load_dotenv
    load_dotenv()
    os.environ.get('environ_name') | os.getenv('environ_name')

# Deploy System environ
## Linux
path

    cd etc/profile

check environ list

    env

check environ value

    echo $key

set environ (temp, env invalid still closed Xshell)

    export environ_name='environ_value'

set environ

    nano etc/profile
    edit: environ_name='environ_value'

# Deploy Project environ
## Django
create the environ file at the project root

    fileName: .env

set the environ in the file of name '.env'

    environ_name='environ_value'
