---
.layout: post
title:  "C#-Extension-合集"
date:   2019-03-17 22:39
categories: C# Extension
tags: C#
---

------

一、去重扩展**Distinct**  

```c#
 /// <summary>
    /// Distinct扩展
    /// </summary>
    /// <typeparam name="T"></typeparam>
    /// <typeparam name="V"></typeparam>
    public class CommonEqualityComparer<T, V> : IEqualityComparer<T>
    {
        private Func<T, V> keySelector;
        private IEqualityComparer<V> comparer;

        public CommonEqualityComparer(Func<T, V> keySelector, IEqualityComparer<V> comparer)
        {
            this.keySelector = keySelector;
            this.comparer = comparer;
        }

        public CommonEqualityComparer(Func<T, V> keySelector): this(keySelector, EqualityComparer<V>.Default)
        { }

        public bool Equals(T x, T y)
        {
            return comparer.Equals(keySelector(x), keySelector(y));
        }

        public int GetHashCode(T obj)
        {
            return comparer.GetHashCode(keySelector(obj));
        }
    }
```

1、引用  

```c#
      public static IEnumerable<T> DIV_Distinct<T, V>(this IEnumerable<T> source, Func<T, V> keySelector)
        {
            return source.Distinct(new CommonEqualityComparer<T, V>(keySelector));
        }
```

> 使用时，可根据多字段去重  
>
> 问题：排序时，使用到了默认的**Distinct**，会默认根据id去重，需要根据别的字段来去重需重新new一下。

***

