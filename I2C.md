# HAL I2C通用驱动

## I2C 软件驱动寄存器结构体

### I2I_InitTypeDef

数据字段：

```c
Data Fields
  	uint32_t ClockSpeed;
	uint32_t DutyCycle;
	uint32_t OwnAddress1;
	uint32_t AddressingMode;
	uint32_t DualAddressingMode;
	uint32_t OwnAddress2;
	uint32_t GeneralCallMode;
	uint32_t NoStretchMode;
```

文档：

- uint32_t I2C_InitTpyeDef::ClockSpeed
- uint32_t I2C_InitTpyeDef::DutyCycle
- uint32_t I2C_InitTypeDef::OwnAddress1
- uint32_t I2C_InitTypeDef::AddressingMode
- uint32_t I2C_InitTypeDef::DualAddressMode
- uint32_t I2C_InitTypeDEf::OwnAddress2
- uint32_t I2C_InitTypeDef::GeneralCallMode
- unit32_t I2C_InitTypeDef::NoStrtchMode

##### HAL_I2C_Mem_Write

功能描述：以阻塞方式将一定量的数据写进特定的内存地址中

参数变量（parameter）：

- hi2c：指向 I2C_Handle TypeDef 结构体的指针，该结构体包含着I2C模块的配置信息
- DevAdress：目标设备的地址
- MemAddress：内部存储器地址
- MemAddSize：内部内存地址的大小
- pData：指向数据缓冲区的指针
- Size：发送数据的大小（Bit/比特）
- Timeout：超时时间（避免程序一直阻塞在此操作中）

return values：HAL status

```c
HAL_I2C_Mem_Write(hi2c, DevAddress, MemAddress, MemAddSize, pData, Size, Timeout);
```

slave address：从地址（IIC通信服从主从，设备地址即从地址，也就是目标设备的地址）

Register Address：寄存器地址（寄存器地址即从属设备中的内存地址）



##### HAL_I2C_Mem_Read
