# Kubernetes 从 0 到 1 学习笔记系列

> 自学 Kubernetes 时整理的三篇图文笔记，用同一个**电商订单·支付微服务平台**案例
> （1 Master + 3 Worker）贯穿始终，覆盖"规划 → 部署 → 数据与可观测性"完整闭环。
> 每篇都是独立的单文件 HTML，直接下载打开浏览器查看即可（含内嵌图解和示意图）。

## 系列目录

| 篇 | 主题 | 覆盖内容 |
|---|---|---|
| [01 · 规划节点与网络](01-planning-and-networking.html) | 集群规划 | 节点选型、三层网段不冲突设计、CNI（Calico）选型、containerd/swap 前置检查 |
| [02 · 引导与工作负载](02-bootstrap-and-workloads.html) | 集群搭建 | `kubeadm init/join`、Deployment / Service / Ingress、HPA 自动扩缩容 |
| [03 · 有状态与可观测性](03-statefulset-and-observability.html) | 数据与监控 | StatefulSet + PV、Secret 管理、Prometheus / Grafana / Loki 全景可观测性闭环 |

## 贯穿的心智模型

三篇笔记共享一条暗线：**`resources.requests`**——从容量规划时的预留，到调度器选节点的依据，
到 HPA 扩缩容的判断基准，再到监控告警的阈值参考，同一个数字贯穿了集群生命周期的每一环。

```
规划 (Planning) → 引导 (Bootstrap) → 部署 (Deploy) → 观测 (Observe)
      ↑                                                    │
      └────────────────── 闭环，数据反哺下一轮规划 ──────────┘
```

## 后续计划补充的方向

- 3 Master 高可用（堆叠 etcd + 负载均衡 VIP）
- GitOps 声明式发布（ArgoCD）
- 云托管 Kubernetes（EKS / GKE / ACK）免运维控制平面

---

这是我从 IT 运维转向 DevOps / SRE 方向的自学笔记之一，边学边整理成图文教程，
方便自己复习，也顺手分享给同样在学 K8s 的人。
