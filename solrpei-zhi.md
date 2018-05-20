各版本solr下载地址[http://archive.apache.org/dist/lucene/solr/](http://archive.apache.org/dist/lucene/solr/)

---

solr语法说明：

| 参数 | 描述 |
| :--- | :--- |
| defType | 指定用于处理查询语句\(参数q的内容\)的查询解析器，eg:defType=lucene |
| sort | 指定响应的排序方式：升序asc或降序desc.同时需要指定按哪个字段进行排序。eg: sort=price desc,score asc |
| start | 指定显示查询结果的开始位置，默认是0 |
| rows | 指定一次显示多少行查询结果，默认是10 |
| fq | 指定用于对查询结果进行过滤的过滤器\(也看作是一种query\) eg: fq=price:\[100 To \*\]&fq=setction:0 |
| fl | 指定查询结果中返回的字段，该字段的stored=”true”或docValues=”true” ,eg:fl=id,title,product\(price, popularity\) |
| debug | 指定查询结果中携带额外的调试信息：时间信息debug=timing，“explain”信息debug=results,所有调试信息debug=query |
| explainOther | Allows clients to specify a Lucene query to identify a set of documents. If non-blank,the explain info of each document which matches this query, relative to the main query \(specified by the q parameter\) will be returned along with the rest of the debugging information. |
| timeAllowed | 指定查询处理的时间，单位毫秒。如果查询在指定的时间未完成，则只返回部分信息 |
| segmentTerminateEarly | Indicates that, if possible, Solr should stop collecting documents from each individual \(sorted\) segment once it can determine that any subsequent documents in that segment will not be candidates for the rows being returned. The default is false. |
| omitHeader | 当设为true时，返回结果不包含头部信息\(例如请求花费的时间等信息\)，默认是false |
| wt | 执行响应的输出格式：xml或json等 |
| logParamsList | 指定哪些参数需要写入log, eg:logParamsList=q,fq |
| echoParams | 指定响应头部包含哪些参数，取值为none/all/explicit\(默认值\) |

---

注意事项

* response.getBeans\(Article.class\)方法需要将Article对应的属性上加上@Field注解



