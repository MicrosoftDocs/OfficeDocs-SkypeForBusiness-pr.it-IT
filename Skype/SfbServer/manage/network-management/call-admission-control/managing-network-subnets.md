---
title: Gestione delle subnet di rete
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nella maggior parte delle distribuzioni di Skype for Business Server in cui è implementato il controllo di ammissione di chiamata, in genere vi sarà un numero elevato di subnet. Per questo motivo, è spesso preferibile configurare le subnet da Skype for Business Server Management Shell.
ms.openlocfilehash: e2ac69190ab93b4b6d81fed13538cc6fcaa91f20
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816396"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Gestione delle subnet di rete in Skype for Business Server

È possibile utilizzare il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell per gestire le subnet di rete. Nella maggior parte delle distribuzioni di Skype for Business Server in cui è implementato il controllo di ammissione di chiamata, in genere vi sarà un numero elevato di subnet. Per questo motivo, è spesso preferibile configurare le subnet da Skype for Business Server Management Shell.

Utilizzare le sezioni di questo articolo per visualizzare le informazioni sulla subnet di rete o creare, modificare o eliminare le subnet di rete. 

## <a name="view-network-subnet-information"></a>Visualizzare le informazioni sulla subnet di rete 

Per visualizzare una subnet di rete è possibile attenersi alla procedura seguente. Dal pannello di controllo di Skype for Business Server, è possibile creare, modificare o eliminare una subnet di rete. 

### <a name="to-view-a-network-subnet"></a>Per visualizzare una subnet di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **Subnet**.

4.  Nella pagina **Subnet** fare clic sulla subnet che si desidera visualizzare.
 
    > [!NOTE]  
    > È possibile visualizzare una sola subnet alla volta.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualizzare le informazioni di configurazione della subnet di rete tramite i cmdlet di Windows PowerShell

È possibile visualizzare le informazioni sulla subnet di rete utilizzando Windows PowerShell e il cmdlet Get-CsNetworkSubnet. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

### <a name="to-view-network-subnet-information"></a>Per visualizzare le informazioni sulla subnet di rete

  - Per visualizzare informazioni su tutte le subnet di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkSubnet
    
    Verranno restituite informazioni simili alle seguenti:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet).


## <a name="create-or-modify-network-subnets"></a>Creare o modificare le subnet di rete 

Una subnet di rete deve essere associata a un sito di rete per la determinazione della posizione geografica dell'host appartenente alla subnet. È possibile utilizzare il pannello di controllo di Skype for Business Server per configurare le subnet. Dal pannello di controllo di Skype for Business Server, è possibile creare, modificare o eliminare una subnet di rete. 

Nella maggior parte delle distribuzioni di Skype for Business Server in cui è implementato il controllo di ammissione di chiamata, in genere vi sarà un numero elevato di subnet. Per questo motivo, è spesso preferibile configurare le subnet da Skype for Business Server Management Shell. Da questa pagina è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet **Import-CSV** di Windows PowerShell. Se si utilizzano questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (con estensione CSV) e creare più subnet contemporaneamente. Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-create-a-network-subnet"></a>Per creare una subnet di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **Subnet**.

4.  Nella pagina **Subnet** fare clic su **Nuovo**.

5.  In **Nuova subnet** immettere un valore nel campo **ID subnet**. Questo valore deve essere il primo indirizzo IP (ad esempio, 174.11.12.0) dell'intervallo di indirizzi IP definito dalla subnet.

6.  Nel campo **Maschera** immettere un valore numerico compreso tra 1 e 32.

    > [!NOTE]  
    > Questo valore corrisponde alla maschera di bit da applicare alla subnet da creare.

7.  In **ID sito di rete** selezionare il sito a cui appartiene la subnet.

8.  (Facoltativo) Digitare un valore nel campo **Descrizione** per fornire ulteriori informazioni sulla subnet che non possono essere espresse dal solo nome.

9.  Fare clic su **Commit**.


### <a name="to-modify-a-network-subnet"></a>Per modificare una subnet di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **Subnet**.

4.  Nella pagina **Subnet** fare clic sulla subnet che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  Nella pagina **Modifica Subnet** è possibile modificare la maschera di bit, il sito di rete associato o la descrizione. Se si modifica la maschera di bit, tenere presente che l'ID subnet deve essere comunque il primo indirizzo IP dell'intervallo di indirizzi IP definito dalla subnet.

7.  Fare clic su **Commit**.

## <a name="delete-network-subnets"></a>Eliminare le subnet di rete

È possibile utilizzare la procedura seguente per eliminare una subnet. Dal pannello di controllo di Skype for Business Server, è possibile creare, modificare o eliminare una subnet di rete. 

Nella maggior parte delle distribuzioni di Skype for Business Server in cui è implementato il controllo di ammissione di chiamata, in genere vi sarà un numero elevato di subnet. Per questo motivo, è spesso preferibile configurare le subnet da Skype for Business Server Management Shell. Da questa pagina è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet **Import-CSV** di Windows PowerShell. Se si utilizzano questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (con estensione CSV) e creare più subnet contemporaneamente. Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-delete-a-network-subnet"></a>Per eliminare una subnet di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **Subnet**.

4.  Nella pagina **Subnet** fare clic sulla subnet che si desidera eliminare.
 
    > [!NOTE]  
    > È possibile eliminare più subnet contemporaneamente. A tale scopo, tenere premuto CTRL e selezionare le diverse subnet. In alternativa, per selezionare tutte le subnet, scegliere **Seleziona tutto** dal menu **Modifica**.

5.  Scegliere **Elimina** dal menu **Modifica**.

6.  Fare clic su **OK**.


## <a name="see-also"></a>Vedere anche

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
