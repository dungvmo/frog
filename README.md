# Install
```bash
 - create virtual environment
 cd frog/
 python3 -m venv env
 source env/bin/activate
 pip install -r requirements.txt
```
 
 # Run
 ```bash
  from frog_app/frog/ run
  python manage.py runserver
```

# Sample

 ```bash

    input: riverWidth: integer number
    leavesPosition: array of integer number

    curl --location --request POST 'http://localhost:8000/' \
    --form 'riverWidth="3"' \
    --form 'leavesPosition="1 2 3"'

    => result: 
    {
        "array": "1,2,3",
        "message": "the frog can cross the river at 2"
    }
```

# Solution 

 ```bash
    get riverWidth and leavesPosition from post request.
    split leavesPosition to list of number => position of the leaves fall
    create a dictionary have keys are 1,2,.. to riverWidth and all default value is empty list [].
    execute for loop over array of position of the leaves fall => get the index of the key 1,2,.. to riverWidth appear the first time 
    each time the key 1,2,.. to riverWidth appear we store the newest index, increase count variable to 1 push that index to value of current key  1,2,.. to riverWidth in dictionary
    the for loop end when count variable = riverWidth or leavesPosition array is ended
    
    => return array and message

```



