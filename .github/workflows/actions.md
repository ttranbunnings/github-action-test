
```yml
     steps:
      - name: Simple JS Action
        id: greet					  (2)
        uses: actions/hello-world-javascript-action@v1    (1)
        with:
          who-to-greet: John
      - name: Log Greeting Time
        run: echo "${{ steps.greet.outputs.time }}"	   (2)
```
(1) v1 is the commit Tag	

(2) By giving `id` to a `steps` we can reference it as a variable


### Checkout action
```yml
steps:
- name: List Files
run: |
	pwd
	ls -a					(1)
- name: Checkout
uses: actions/checkout@v1			(2)

- name: List Files after checkout
run: |
	pwd
	ls -a					(3)
```

(1) When the action first run, the current directory should be empty	

(2) This is almost a equivalent of 
```bash
echo $GITHUB_SHA    #get the current commit id
echo $GITHUB_REPOSITORY  #get current github repo
echo $GITHUB_WORKSPACE #get current github workspace path
echo "${{ github.token}}"

```

 The current branch (master) will be check out	

(3) Current directory should have all the files of the checkout branch.


## Actions can be found via [Github Marketplace](https://github.com/marketplace)

## Event that trigger Workflow [Documentation](https://docs.github.com/en/actions/reference/events-that-trigger-workflows#pull_request)

## Cron tap : https://crontab.guru/#0/15_*_*_*_*