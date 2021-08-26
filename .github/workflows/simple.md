Events: on 
```yml
on: [push, pull_request, pull_request_review, schedule ]
```

To run multiple command use `|` eg:
```yml
run: |
	node -v
	npm -v
```