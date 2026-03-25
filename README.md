# Arquitetura Kubernets
<img width="5065" height="1628" alt="image" src="https://github.com/user-attachments/assets/f9dd5704-6cf3-4cb2-bb87-ceae200c504c" />

# Arquitetura Kubernets: Exempo prático 

<img width="2900" height="1573" alt="image" src="https://github.com/user-attachments/assets/266fd45c-0c03-4156-88d5-b324fd52bce7" />

# Comunicação 
| Componente | Porta | Protocolo | Tipo |
|---|---|---|---|
| kube-apiserver | 6443 | TCP | Control Plane |
| etcd | 2379–2380 | TCP | Control Plane |
| kube-scheduler | 10251 | TCP | Control Plane |
| kubelet | 10250 | TCP | Node (Worker) |
| kube-controller-manager | 10252 | TCP | Control Plane |
| NodePort (Service) | 30000–32767 | TCP/UDP | Node (Worker) |
| Weave Net | 6783–6784 | TCP/UDP | Node (Worker) |

# Gerenciamento de nodes e pods: 

<img width="3274" height="2401" alt="image" src="https://github.com/user-attachments/assets/2e7a43f4-e4de-47c8-b1a7-66052a5e4aa2" />

## Conceitos‑chave do Kubernetes

Conceitos fundamentais para entender como o Kubernetes orquestra aplicações: ele não gerencia contêineres diretamente, e sim por meio de **Pods**.

- **Pod:** menor unidade do Kubernetes. Contêineres são organizados dentro de Pods, que compartilham recursos como rede (IP/porta), volumes e limites de CPU e memória. Um Pod pode conter um ou mais contêineres.
- **Deployment:** um dos controllers mais usados. Em conjunto com o **ReplicaSet**, garante que a quantidade desejada de réplicas (Pods) esteja em execução nos nós *workers*. Também gerencia o ciclo de vida da aplicação, como criação, atualização e remoção. Parâmetros como imagem, portas, volumes e variáveis de ambiente podem ser definidos em manifestos **YAML/JSON** e aplicados via `kubectl`.
- **ReplicaSet:** objeto responsável por manter a quantidade desejada de Pods em execução.
- **Service:** expõe e estabiliza o acesso aos Pods, distribuindo as requisições entre as réplicas (balanceamento). Pode ser do tipo **ClusterIP**, **NodePort** ou **LoadBalancer**
