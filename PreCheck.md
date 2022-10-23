# 通用检测项预检

## 检测项1

通过要求：

- 在anyshare命名空间下，所有pod处于running

pod状态应该只有以下三种

- running
- waiting
- terminated

对应API文档（pod）

https://github.com/kubernetes-client/python/blob/master/kubernetes/docs/V1PodList.md


对应API文档（Node）

https://github.com/kubernetes-client/python/blob/master/kubernetes/docs/V1NodeList.md
