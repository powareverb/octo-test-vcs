# Notes

```terraform
terraform plan -out plan.tfplan
terraform show -json plan.tfplan > plan.tfplan.json
terraform graph

terraform graph -type=plan | dot -Tpng -o graph.png

terraform apply
```

```pwsh
# Custom plan
terraform plan -out plan.tfplan
terraform show -json plan.tfplan > plan.tfplan.json

$plan = Get-Content .\plan.tfplan.json | ConvertFrom-Json
$drift = $plan.resource_drift | %{ $_.change.actions }
$change = $plan.resource_changes | %{ $_.change.actions }
```
