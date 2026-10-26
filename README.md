# 电控组第二次培训作业

- **朱章铭**
- ***20263008273***

基于 GPIO 的推挽输出 + HAL_Delay 等待。CubeMX 中将 PA0、PA1、PA2 配置为推挽输出，并用 User Label 分别命名为 LED0、LED1、LED2，代码通过 `LED0_Pin` 等宏控制三灯依次点亮，间隔 500ms。
本来想做加分项的 但是还没有学到（逃）

```c
while (1)
{
    HAL_GPIO_WritePin(LED0_GPIO_Port, LED0_Pin, GPIO_PIN_SET);          //led0
    HAL_GPIO_WritePin(LED1_GPIO_Port, LED1_Pin, GPIO_PIN_RESET);
    HAL_GPIO_WritePin(LED2_GPIO_Port, LED2_Pin, GPIO_PIN_RESET);
    HAL_Delay(500);

    HAL_GPIO_WritePin(LED0_GPIO_Port, LED0_Pin, GPIO_PIN_RESET);            //led1
    HAL_GPIO_WritePin(LED1_GPIO_Port, LED1_Pin, GPIO_PIN_SET);
    HAL_GPIO_WritePin(LED2_GPIO_Port, LED2_Pin, GPIO_PIN_RESET);
    HAL_Delay(500);

    HAL_GPIO_WritePin(LED0_GPIO_Port, LED0_Pin, GPIO_PIN_RESET);            //led2
    HAL_GPIO_WritePin(LED1_GPIO_Port, LED1_Pin, GPIO_PIN_RESET);
    HAL_GPIO_WritePin(LED2_GPIO_Port, LED2_Pin, GPIO_PIN_SET);
    HAL_Delay(500);
}
```

演示视频：[演示视频.mp4](演示视频.mp4)