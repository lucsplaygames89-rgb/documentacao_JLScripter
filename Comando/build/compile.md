# `jls compile`

Gera bytecode JLScript `.jlb`.

```powershell
jls compile <arquivo.jls> [-o <arquivo.jlb>]
```

Opções:

- `-o`, `--output`: caminho de saída.
- `-h`, `--help`: ajuda.

A entrada precisa existir. A implementação usa `BytecodeCompiler` e, sem saída personalizada, informa que o bytecode foi gerado em `build/`.
