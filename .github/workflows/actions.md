
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