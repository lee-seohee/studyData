"logic gate" 

* Registers: A group of flip-flops together with gates to store binary information
* Counter: A special type of register that goes through a predetermined sequence of states

### Mode Control (S1, S0)
       Register Operation
(0, 0) No change
(0, 1) Shift right
(1, 0) Shift left
(1, 1) Parallel load

### 카운터(Counter)
* 동기식 카운터 vs 비동기식 카운터(리플 ripple 카운터(대표적인 비동기식 카운터))
* 업 카운터(스톱워치) vs 다운 카운터(타이머)
* 이진 카운터 vs BCD 카운터(10진 카운터)
* 링 카운터 - 초기값을 1000으로 세팅해야 함(Counter와 decoder를 활용하면 초기값을 세팅할 필요 없음)
* JohnsonCounter(E' 값을 A에 전달하는 카운터)