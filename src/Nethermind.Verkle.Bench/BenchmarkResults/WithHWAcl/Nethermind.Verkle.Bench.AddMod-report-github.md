``` ini

BenchmarkDotNet=v0.13.2, OS=pop 22.04
AMD Ryzen 9 7900X, 1 CPU, 24 logical and 12 physical cores
.NET SDK=7.0.203
  [Host]   : .NET 7.0.5 (7.0.523.17405), X64 RyuJIT AVX2
  .NET 7.0 : .NET 7.0.5 (7.0.523.17405), X64 RyuJIT AVX2

Job=.NET 7.0  Runtime=.NET 7.0

```

| Method                | _a                      | _b                      |          Mean |         Error |        StdDev |    Ratio |  RatioSD |       Gen0 | Allocated | Alloc Ratio |
|-----------------------|-------------------------|-------------------------|--------------:|--------------:|--------------:|---------:|---------:|-----------:|----------:|------------:|
| **AddMod_BigInteger** | **(115(...)FpE) [201]** | **(115(...)FpE) [201]** | **43.283 ns** | **0.4104 ns** | **0.3839 ns** | **1.00** | **0.00** | **0.0014** | **120 B** |    **1.00** |
| AddMod_BigInteger_New | (115(...)FpE) [201]     | (115(...)FpE) [201]     |     45.973 ns |     0.2329 ns |     0.2179 ns |     1.06 |     0.01 |     0.0014 |     120 B |        1.00 |
| AddMod_UInt256        | (115(...)FpE) [201]     | (115(...)FpE) [201]     |     53.137 ns |     0.3435 ns |     0.3213 ns |     1.23 |     0.02 |          - |         - |        0.00 |
| AddMod_Element        | (115(...)FpE) [201]     | (115(...)FpE) [201]     |      5.253 ns |     0.0897 ns |     0.0839 ns |     0.12 |     0.00 |          - |         - |        0.00 |
|                       |                         |                         |               |               |               |          |          |            |           |             |
| **AddMod_BigInteger** | **(115(...)FpE) [201]** | **(619(...)FpE) [197]** | **42.005 ns** | **0.0824 ns** | **0.0771 ns** | **1.00** | **0.00** | **0.0014** | **120 B** |    **1.00** |
| AddMod_BigInteger_New | (115(...)FpE) [201]     | (619(...)FpE) [197]     |     42.456 ns |     0.3038 ns |     0.2842 ns |     1.01 |     0.01 |     0.0014 |     120 B |        1.00 |
| AddMod_UInt256        | (115(...)FpE) [201]     | (619(...)FpE) [197]     |     53.533 ns |     0.6439 ns |     0.6023 ns |     1.27 |     0.01 |          - |         - |        0.00 |
| AddMod_Element        | (115(...)FpE) [201]     | (619(...)FpE) [197]     |      5.493 ns |     0.0914 ns |     0.0855 ns |     0.13 |     0.00 |          - |         - |        0.00 |
|                       |                         |                         |               |               |               |          |          |            |           |             |
| **AddMod_BigInteger** | **(619(...)FpE) [197]** | **(115(...)FpE) [201]** | **42.326 ns** | **0.3523 ns** | **0.2942 ns** | **1.00** | **0.00** | **0.0014** | **120 B** |    **1.00** |
| AddMod_BigInteger_New | (619(...)FpE) [197]     | (115(...)FpE) [201]     |     42.098 ns |     0.1867 ns |     0.1746 ns |     0.99 |     0.01 |     0.0014 |     120 B |        1.00 |
| AddMod_UInt256        | (619(...)FpE) [197]     | (115(...)FpE) [201]     |     52.583 ns |     0.0758 ns |     0.0709 ns |     1.24 |     0.01 |          - |         - |        0.00 |
| AddMod_Element        | (619(...)FpE) [197]     | (115(...)FpE) [201]     |      5.127 ns |     0.0233 ns |     0.0218 ns |     0.12 |     0.00 |          - |         - |        0.00 |
|                       |                         |                         |               |               |               |          |          |            |           |             |
| **AddMod_BigInteger** | **(619(...)FpE) [197]** | **(619(...)FpE) [197]** | **32.822 ns** | **0.2576 ns** | **0.2284 ns** | **1.00** | **0.00** | **0.0013** | **112 B** |    **1.00** |
| AddMod_BigInteger_New | (619(...)FpE) [197]     | (619(...)FpE) [197]     |     33.582 ns |     0.4699 ns |     0.4166 ns |     1.02 |     0.01 |     0.0013 |     112 B |        1.00 |
| AddMod_UInt256        | (619(...)FpE) [197]     | (619(...)FpE) [197]     |      9.117 ns |     0.0569 ns |     0.0505 ns |     0.28 |     0.00 |          - |         - |        0.00 |
| AddMod_Element        | (619(...)FpE) [197]     | (619(...)FpE) [197]     |      5.129 ns |     0.0765 ns |     0.0715 ns |     0.16 |     0.00 |          - |         - |        0.00 |