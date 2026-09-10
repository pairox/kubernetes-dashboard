resource "helm_release" "kubernetes_dashboard" {
  name             = "kubernetes-dashboard"
  namespace        = "kubernetes-dashboard"
  create_namespace = true

  repository = "https://pairox.github.io/kubernetes-dashboard/"
  chart      = "kubernetes-dashboard"

  set {
    name  = "app.scheduling.nodeSelector.node"
    value = "pairox"
  }

  set {
    name  = "auth.nodeSelector.node"
    value = "pairox"
  }
}