
## 创建/编辑Node镜像
1. Git clone git@gitlab.xxxxxx.com:utils/deploy.git
2. cd node/docker
3. bash build.sh (docker build)
4. docker push  xhj-prod-registry-vpc.cn-hangzhou.cr.aliyuncs.com/xhj-image-common/node-base:14.17.4
5. docker run -it  xhj-prod-registry-vpc.cn-hangzhou.cr.aliyuncs.com/xhj-image-common/node-base:14.17.4 -- bash

## 查看image镜像，并拉取镜像 到本地
1. docker pull    xhj-prod-registry-vpc.cn-hangzhou.cr.aliyuncs.com/xhj-image-common/node-base:14.17.4
2. docker run -it xhj-prod-registry-vpc.cn-hangzhou.cr.aliyuncs.com/xhj-image-common/node-base:14.17.4 bash

## 测试环境deploy： 
#### 线上调试方法：
https://shimo.im/docs/KKX6VtVqRvHjdKk6/read
aliyunJumper
`> airent.k8s.master   172.16.0.205:22    ssh   root`
#### 获取pods
saaskubectl get pods -n deployment-prod 
#### 进入pods
saaskubectlprod exec -it saas-bff-6f6cdf648-hhb24 -n deployment-prod -- bash 
#### 进入pods别名 [cat .zshrc]
nodesaas 

alias saaskubectl="kubectl --kubeconfig=/root/.kube/saas_config”

alias saasnode1="saaskubectl exec -it $(saaskubectl get pods -n deployment-prod|grep saas-bff|head -n 1|awk '{print $1}') -n deployment-prod — bash

alias saasnode2="saaskubectl exec -it $(saaskubectl get pods -n deployment-prod|grep saas-bff|tail -n 1|awk '{print $1}') -n deployment-prod -- bash"
#### 获取 deployment
saaskubectl get deployment -n deployment-prod
#### 删除容器
saaskubectl delete pod saas-opensaas-7c6fb9dcdf-bkpk9 -n deployment-prod
#### 扩容[调试使用]
history|grep ‘scale’

saaskubectl  -n deployment-beta scale deployment saas-bff --replicas=1

saaskubectlprod scale deployment saas-bff --replicas=2

kubectl get deployment -n deployment-test|grep 'bff'

kubectl delete deployment saas-bff-test1666 -n deployment-test
### 版本回退
#### 查看发布历史
kubectl rollout history deployment.v1.apps/nginx-deployment

saaskubectlprod rollout history deployment airent-web-saas-bff

saaskubectlprod rollout undo deployment airent-web-saas-bff --to-revision=xx

saaskubectlprod rollout restart deployment  airent-web-saas-bff

### 高阶用法

#### 查看宿主机日志路径
> saaskubectlprod get pods -o wide |grep saas-bff
> saaskubectl -n kube-system get pods -o wide |grep cn-hangzhou.172.19.0.115|grep log
> saaskubectl -n kube-system exec -it xhj-log-manager-h5q95 bash

> saaskubectl -n kube-system get pods -o wide |grep cn-hangzhou.172.19.0.163|grep log
> kubectl -n istio-system get pods    #获取istio-system的pods
#### 查看istio的日志
> kubectl -n istio-system logs -f istio-ingressgateway-69c74dd556-szcsz --tail=20|grep zhixiangyao
> kubectl -n deployment-test describe pod recovery-bff-test888-7cf896fdd8-lbpzd
> saaskubectlprod get gw common-gateway-eshetang -o yaml
> saaskubectlprod get virtualservice saas-erp-eshetang-vs -o yaml > /tmp/vs.yaml
> saaskubectl apply -f /tmp/vs.yaml
