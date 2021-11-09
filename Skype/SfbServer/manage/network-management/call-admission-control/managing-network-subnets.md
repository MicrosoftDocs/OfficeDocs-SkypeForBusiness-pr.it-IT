---
title: Gestione delle subnet di rete
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Nella maggior parte delle distribuzioni di Skype for Business Server in cui è implementato il servizio Controllo di ammissione di chiamata, in genere è presente un numero elevato di subnet. Per questo, spesso è meglio configurare le subnet da Skype for Business Server Management Shell.
ms.openlocfilehash: 73a0f99fa35cd1b92194ce5b09d85a30d30b72e2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843859"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Gestione delle subnet di rete in Skype for Business Server

È possibile utilizzare il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell per gestire le subnet di rete. Nella maggior parte delle distribuzioni di Skype for Business Server in cui è implementato il servizio Controllo di ammissione di chiamata, in genere è presente un numero elevato di subnet. Per questo, spesso è meglio configurare le subnet da Skype for Business Server Management Shell.

Utilizzare le sezioni di questo articolo per visualizzare le informazioni sulle subnet di rete oppure per creare, modificare o eliminare subnet di rete. 

## <a name="view-network-subnet-information"></a>Visualizzare le informazioni sulla subnet di rete 

Per visualizzare una subnet di rete è possibile attenersi alla procedura seguente. Dal Pannello Skype for Business Server di controllo è possibile creare, modificare o eliminare una subnet di rete. 

### <a name="to-view-a-network-subnet"></a>Per visualizzare una subnet di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet.**

4.  Nella pagina **Subnet** fare clic sulla subnet che si desidera visualizzare.
 
    > [!NOTE]
    > È possibile visualizzare una sola subnet alla volta.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualizzare le informazioni sulla configurazione della subnet di rete utilizzando Windows PowerShell cmdlet

Le informazioni sulla subnet di rete possono essere visualizzate utilizzando Windows PowerShell e il cmdlet Get-CsNetworkSubnet rete. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

### <a name="to-view-network-subnet-information"></a>Per visualizzare le informazioni sulla subnet di rete

  - Per visualizzare informazioni su tutte le subnet di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
    **Get-CsNetworkSubnet**
    
    Verranno restituite informazioni simili alle seguenti:
    
    Identity : 172.11.15.0<br/>
    MaskBits : 28<br/>
    Descrizione :<br/>
    NetworkSiteID : Redmond<br/>
    SubnetID : 172.11.15.0<br/>


Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet).


## <a name="create-or-modify-network-subnets"></a>Creare o modificare subnet di rete 

Una subnet di rete deve essere associata a un sito di rete per la determinazione della posizione geografica dell'host appartenente alla subnet. È possibile utilizzare il Pannello Skype for Business Server per configurare le subnet. Dal Pannello Skype for Business Server di controllo è possibile creare, modificare o eliminare una subnet di rete. 

Nella maggior parte delle distribuzioni di Skype for Business Server in cui è implementato il servizio Controllo di ammissione di chiamata, in genere è presente un numero elevato di subnet. Per questo, spesso è meglio configurare le subnet da Skype for Business Server Management Shell. Da qui è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet **Windows PowerShell Import-CSV**. Utilizzando questi cmdlet insieme, è possibile leggere le impostazioni delle subnet da un file con valori delimitati da virgole (.csv) e creare più subnet contemporaneamente. Per esempi su come creare subnet da un file .csv, vedere [New-CsNetworkSubnet.](/powershell/module/skype/New-CsNetworkSubnet)


### <a name="to-create-a-network-subnet"></a>Per creare una subnet di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet.**

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

2.  Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet.**

4.  Nella pagina **Subnet** fare clic sulla subnet che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  Nella pagina **Modifica Subnet** è possibile modificare la maschera di bit, il sito di rete associato o la descrizione. Se si modifica la maschera di bit, tenere presente che l'ID subnet deve essere comunque il primo indirizzo IP dell'intervallo di indirizzi IP definito dalla subnet.

7.  Fare clic su **Commit**.

## <a name="delete-network-subnets"></a>Eliminare subnet di rete

È possibile utilizzare la procedura seguente per eliminare una subnet. Dal Pannello Skype for Business Server di controllo è possibile creare, modificare o eliminare una subnet di rete. 

Nella maggior parte delle distribuzioni di Skype for Business Server in cui è implementato il servizio Controllo di ammissione di chiamata, in genere è presente un numero elevato di subnet. Per questo, spesso è meglio configurare le subnet da Skype for Business Server Management Shell. Da qui è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet **Windows PowerShell Import-CSV**. Utilizzando questi cmdlet insieme, è possibile leggere le impostazioni delle subnet da un file con valori delimitati da virgole (.csv) e creare più subnet contemporaneamente. Per esempi su come creare subnet da un file .csv, vedere [New-CsNetworkSubnet.](/powershell/module/skype/New-CsNetworkSubnet)


### <a name="to-delete-a-network-subnet"></a>Per eliminare una subnet di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet.**

4.  Nella pagina **Subnet** fare clic sulla subnet che si desidera eliminare.
 
    > [!NOTE]  
    > È possibile eliminare più subnet contemporaneamente. A tale scopo, tenere premuto CTRL e selezionare le diverse subnet. In alternativa, per selezionare tutte le subnet, scegliere **Seleziona tutto** dal menu **Modifica**.

5.  Scegliere **Elimina** dal menu **Modifica**.

6.  Fare clic su **OK**.


## <a name="see-also"></a>Vedere anche

[New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet)