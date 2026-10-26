Use [[D Flip-Flop|D Flip-Flops]] in-between each pipeline stage to control the flow of data.
#### Hazards
```
lw     t2, 0(t1)
add    t3, t3, t2
```
- This has a load-to-use dependency on register t2