---
title: "State Backends"
nav-parent_id: streaming_state
nav-pos: 5
---
<!--
Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements.  See the NOTICE file
distributed with this work for additional information
regarding copyright ownership.  The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License.  You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied.  See the License for the
specific language governing permissions and limitations
under the License.
-->

Flink 提供了不同的 `State Backends`，用于指定存储状态的方式和位置。

状态可以位于Java堆或堆中。根据你的 `State Backend`，Flink 还可以管理应用程序的状态，这意味着 Flink 处理内存管理（如果需要，可能会溢出到磁盘），以允许应用程序保持大体量的状态。默认情况下，可通过配置文件 flink-conf.yaml 确定所有 flink job 的State Backend。

但是，默认的 `State Backend` 可以被独立的 job 覆盖，如下所示。

有关可用 `State Backend` 及其优势、限制和配置参数的详细信息，请参阅 [部署和操作](site.baseurl/ops/state/state_backends.html) 中的相应部分。

<div class="codetabs" markdown="1">
<div data-lang="java" markdown="1">
{% highlight java %}
StreamExecutionEnvironment env = StreamExecutionEnvironment.getExecutionEnvironment();
env.setStateBackend(...);
{% endhighlight %}
</div>
<div data-lang="scala" markdown="1">
{% highlight scala %}
val env = StreamExecutionEnvironment.getExecutionEnvironment()
env.setStateBackend(...)
{% endhighlight %}
</div>
</div>

{% top %}
