# Object Query Language

```
select filter(heap.classes(), "/java.net./.test(it.name)")
```

```
select count(heap.classes(), "/com.zzz./.test(it.name)")
```

```
 select map(filter(heap.classes(), "/java.net./.test(it.name)"),
      function (it) {
         var res = '';
         while (it != null) {
            res += toHtml(it) + "->";
            it = it.parent;
         }
         res += "null";
         return res + "<br>";
      })
```

# Filtered count
```
select map(filter(heap.classes(), "/eclipse./.test(it.name)"),
      function (it) {
         var res = '';
         var cnt=0;
         while (it != null) {
            objs = heap.objects(it);
            cnt= count(objs);
            if (cnt>10) {
res += "<br/>"+toHtml(it) + "-> Count: "+cnt;
           }
            it = it.next;
         }
         return res ;
      })

```

# Compute size
```
  select sum(map(heap.objects("lombok.eclipse.EclipseNode"), 'sizeof(it)'))

```
