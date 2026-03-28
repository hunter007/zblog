---
title: Fmt
slug: fmt
date: 2026-03-28T12:34:18+08:00
# lastmod: 2026-03-28T12:34:18+08:00 # Last modification date
tags:
  - golang
categories:
  - golang
# draft: true
---

fmt包有3类API：
- Printing
- Scaning
- error

Printing类API：
1.输出到os.Stdout：Print      Println       Printf
2.返回string：          Sprint    Sprintln     Sprintf
3.写入 io.Writer：     Fprint     Fprintln     Fprintf
4.输出到 []byte：     Append  Appendln  Appendf

Scaning类API
1.从os.Stdin读入： Scan  Scanln   Scanf
2.从io.Reader读入：Fscan  Fscanln  Fscanf
3.从argument string读入：Sscan  Sscanln  Sscanf


Error类API
Errorf(format string, a ...any) (err error)

对于任何用户定义的数据结构，实现fmt.Formatter 和 fmt.Stringer

```golang {linenos=inline  style=monokai}
type Stringer interface {
    String() string
}
```



```golang {linenos=inline  style=monokai}
type Formatter interface {
    Format(f State, verb rune)
}
```

```golang {linenos=inline style=monokai}
type Scanner interface {
    Scan(state ScanState, verb rune) error
}
```
