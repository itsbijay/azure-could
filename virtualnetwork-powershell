New-AzResourceGroup -Name myResourceGroup -Location EastUS

$virtualNetwork = New-AzVirtualNetwork `
-ResourceGroupName myResourceGroup `
-Location EastUS `
-Name myVirtualNetwork `
-AddressPrefix 10.0.0.0/16

$subnetConfig = Add-AzVirtualNetworkSubnetConfig `
-Name default `
-AddressPrefix 10.0.0.0/24 `
-VirtualNetwork $virtualNetwork

$virtualNetwork | Set-AzVirtualNetwork


New-AzVm `
-ResourceGroupName "myResourceGroup" `
-Location "East US" `
-VirtualNetworkName "myVirtualNetwork" `
-SubnetName "default" `
-Name "myVm1" `
-AsJob


New-AzVm `
-ResourceGroupName "myResourceGroup" `
-VirtualNetworkName "myVirtualNetwork" `
-SubnetName "default" `
-Name "myVm2"


Get-AzPublicIpAddress `
-Name myVm1 `
-ResourceGroupName myResourceGroup `
| Select IpAddress


mstsc /v:<publicIpAddress>


Remove-AzResourceGroup -Name myResourceGroup -Force
