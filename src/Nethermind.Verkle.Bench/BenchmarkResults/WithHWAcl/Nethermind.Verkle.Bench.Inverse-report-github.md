``` ini

BenchmarkDotNet=v0.13.2, OS=pop 22.04
AMD Ryzen 9 7900X, 1 CPU, 24 logical and 12 physical cores
.NET SDK=7.0.203
  [Host]   : .NET 7.0.5 (7.0.523.17405), X64 RyuJIT AVX2
  .NET 7.0 : .NET 7.0.5 (7.0.523.17405), X64 RyuJIT AVX2

Job=.NET 7.0  Runtime=.NET 7.0

```

| Method                 | _a                      | _b                      |          Mean |         Error |        StdDev |        Median |    Ratio |  RatioSD | Allocated | Alloc Ratio |
|------------------------|-------------------------|-------------------------|--------------:|--------------:|--------------:|--------------:|---------:|---------:|----------:|------------:|
| **Inverse_BigInteger** | **(115(...)FpE) [201]** | **(115(...)FpE) [201]** | **59.832 μs** | **1.1917 μs** | **3.5138 μs** | **61.124 μs** | **1.00** | **0.00** | **112 B** |    **1.00** |
| Inverse_UInt256        | (115(...)FpE) [201]     | (115(...)FpE) [201]     |     48.948 μs |     0.5049 μs |     0.4723 μs |     48.808 μs |     0.79 |     0.03 |         - |        0.00 |
| Inverse_Element        | (115(...)FpE) [201]     | (115(...)FpE) [201]     |      4.041 μs |     0.0068 μs |     0.0060 μs |      4.038 μs |     0.06 |     0.00 |         - |        0.00 |
|                        |                         |                         |               |               |               |               |          |          |           |             |
| **Inverse_BigInteger** | **(115(...)FpE) [201]** | **(619(...)FpE) [197]** | **60.753 μs** | **1.2098 μs** | **3.0128 μs** | **61.920 μs** | **1.00** | **0.00** | **112 B** |    **1.00** |
| Inverse_UInt256        | (115(...)FpE) [201]     | (619(...)FpE) [197]     |     48.153 μs |     0.4582 μs |     0.4286 μs |     47.968 μs |     0.81 |     0.07 |         - |        0.00 |
| Inverse_Element        | (115(...)FpE) [201]     | (619(...)FpE) [197]     |      3.961 μs |     0.0076 μs |     0.0071 μs |      3.961 μs |     0.07 |     0.00 |         - |        0.00 |
|                        |                         |                         |               |               |               |               |          |          |           |             |
| **Inverse_BigInteger** | **(619(...)FpE) [197]** | **(115(...)FpE) [201]** | **53.259 μs** | **0.3478 μs** | **0.2904 μs** | **53.207 μs** | **1.00** | **0.00** | **112 B** |    **1.00** |
| Inverse_UInt256        | (619(...)FpE) [197]     | (115(...)FpE) [201]     |     46.035 μs |     0.4384 μs |     0.4101 μs |     45.771 μs |     0.86 |     0.01 |         - |        0.00 |
| Inverse_Element        | (619(...)FpE) [197]     | (115(...)FpE) [201]     |      4.072 μs |     0.0088 μs |     0.0082 μs |      4.070 μs |     0.08 |     0.00 |         - |        0.00 |
|                        |                         |                         |               |               |               |               |          |          |           |             |
| **Inverse_BigInteger** | **(619(...)FpE) [197]** | **(619(...)FpE) [197]** | **63.957 μs** | **2.1586 μs** | **6.3647 μs** | **66.892 μs** | **1.00** | **0.00** | **112 B** |    **1.00** |
| Inverse_UInt256        | (619(...)FpE) [197]     | (619(...)FpE) [197]     |     47.232 μs |     0.4343 μs |     0.3850 μs |     47.169 μs |     0.78 |     0.08 |         - |        0.00 |
| Inverse_Element        | (619(...)FpE) [197]     | (619(...)FpE) [197]     |      4.120 μs |     0.0121 μs |     0.0101 μs |      4.116 μs |     0.07 |     0.01 |         - |        0.00 |