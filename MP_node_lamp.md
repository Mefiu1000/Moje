# MP_node_lamp
Addresses:

TxID: **0x1E**

RxID: **0x1F**

# Request
1) Odczytanie stanu lampy:
 
|RxID  |2      |0x3D   |0x0A   |
|------|-------|-------|-------|
|      |DLC    |READ   |RegID  |


2) Zmiana stanu lampy:
 
|RxID  |3      |0x2D   |0x0A   |Light_value|     
|------|-------|-------|-------|-----------|
|      |DLC    |WRITE  |RegID  |data[7-0]  |
Light_value:(1-ON,0-OFF)

3) Encoder filtered value:
 
|RxID  |2      |0x3D   |0x03   |
|------|-------|-------|-------|
|      |DLC    |READ   |RegID  |

4) ADC filtered value:
 
|RxID  |2      |0x3D   |0x04   |
|------|-------|-------|-------|
|      |DLC    |READ   |RegID  |

# Respond
1) Odczytanie stanu lampy:
 
|TxID  |2      |0x0A   |Light_value|Range |Units    |
|------|-------|-------|---------- |------|---------|
|      |DLC    |RegID  |data[7-0]  |16bit |+/-32767 |

2) Zmiana stanu lampy:
 
|TxID  |2      |0x0A   |Light_value|Range |Units    |     
|------|-------|-------|-----------|------|---------|
|      |DLC    |RegID  |data[7-0]  |16bit |+/-32767 |

# Error list
1) Zwarcie:

|TxID  |2      |0x1D   |0x02   |
|------|-------|-------|-------|
|      |DLC    |ERROR  |Code   |
2) Przepalenie diody:

|TxID  |2      |0x1D   |0x03   |
|------|-------|-------|-------|
|      |DLC    |ERROR  |Code   |
3) Blad nieznany:

|TxID  |2      |0x1D   |0x04   |
|------|-------|-------|-------|
|      |DLC    |ERROR  |Code   |

