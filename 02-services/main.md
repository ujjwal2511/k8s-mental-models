KUBERNETES CLUSTER
                                KUBERNETES CLUSTER

                         +--------------------------------------+
                         |                                      |
                         |          LoadBalancer Service         |
Internet                 |        (Public Front Door)           |
    │                    |                 │                    |
    ▼                    |                 ▼                    |
+---------+              |          NodePort Service            |
|  User   |─────────────▶|     (Door on Every Node)             |
+---------+              |                 │                    |
                         |                 ▼                    |
                         |          ClusterIP Service           |
                         |      (Internal Stable Address)       |
                         |                 │                    |
                         |     Uses Selector: app=payment       |
                         |                 │                    |
                         |      Finds Pods with Labels          |
                         |                 │                    |
                         |      ┌──────────┼──────────┐         |
                         |      ▼          ▼          ▼         |
                         |   Pod A      Pod B      Pod C        |
                         | app=payment app=payment app=payment  |
                         |      │          │          │         |
                         |      ▼          ▼          ▼         |
                         | Containers  Containers  Containers   |
                         +--------------------------------------+