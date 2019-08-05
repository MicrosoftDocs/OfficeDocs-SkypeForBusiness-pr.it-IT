---
title: Gestione delle subnet di rete
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nella maggior parte delle distribuzioni di Skype for Business Server in cui viene implementato il controllo di ammissione di chiamata (CAC), in genere ci sarà un numero elevato di subnet. Per questo motivo, è spesso consigliabile configurare subnet da Skype for Business Server Management Shell.
ms.openlocfilehash: 354dd43fd526ba2a6c6f88c8e1f30d0aae37b3bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188558"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>Gestione delle subnet di rete in Skype for Business Server

Puoi usare il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell per gestire le subnet di rete. Nella maggior parte delle distribuzioni di Skype for Business Server in cui viene implementato il controllo di ammissione di chiamata (CAC), in genere ci sarà un numero elevato di subnet. Per questo motivo, è spesso consigliabile configurare subnet da Skype for Business Server Management Shell.

Usare le sezioni di questo articolo per visualizzare le informazioni sulla subnet di rete o per creare, modificare o eliminare subnet di rete. 

## <a name="view-network-subnet-information"></a>Visualizzare le informazioni sulla subnet di rete 

Per visualizzare una subnet di rete, è possibile usare la procedura seguente. Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare una subnet di rete. 

### <a name="to-view-a-network-subnet"></a>Per visualizzare una subnet di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi fare clic su **Subnet**.

4.  Nella pagina **subnet** fare clic sulla subnet che si desidera visualizzare.
 
    > [!NOTE]  
    > È possibile visualizzare una sola subnet alla volta.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualizzare le informazioni di configurazione della subnet di rete usando i cmdlet di Windows PowerShell

Le informazioni sulla subnet di rete possono essere visualizzate usando Windows PowerShell e il cmdlet Get-CsNetworkSubnet. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

### <a name="to-view-network-subnet-information"></a>Per visualizzare le informazioni sulla subnet di rete

  - Per visualizzare informazioni su tutte le subnet di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkSubnet
    
    Questo restituirà informazioni simili alla seguente:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .


## <a name="create-or-modify-network-subnets"></a>Creare o modificare subnet di rete 

Una subnet di rete deve essere associata a un sito di rete allo scopo di determinare la posizione geografica dell'host appartenente alla subnet. Puoi usare il pannello di controllo di Skype for Business Server per configurare le subnet. Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare una subnet di rete. 

Nella maggior parte delle distribuzioni di Skype for Business Server in cui viene implementato il controllo di ammissione di chiamata (CAC), in genere ci sarà un numero elevato di subnet. Per questo motivo, è spesso consigliabile configurare subnet da Skype for Business Server Management Shell. Da lì è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet di Windows PowerShell **Import-CSV**. Usando questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (CSV) e creare più subnet contemporaneamente. Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-create-a-network-subnet"></a>Per creare una subnet di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi fare clic su **Subnet**.

4.  Nella pagina **subnet** fare clic su **nuovo**.

5.  Nella **nuova subnet**immettere un valore nel campo **ID Subnet** . Deve essere un indirizzo IP, ad esempio 174.11.12.0, e deve essere il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet.

6.  Nel campo **maschera** immettere un valore numerico compreso tra 1 e 32.

    > [!NOTE]  
    > Questo valore è la maschera di maschere che deve essere applicata alla subnet da creare.

7.  In **ID sito di rete**selezionare il sito a cui appartiene la subnet.

8.  Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni su questa subnet che non può essere espressa solo dal nome.

9.  Fare clic su **Commit**.


### <a name="to-modify-a-network-subnet"></a>Per modificare una subnet di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi fare clic su **Subnet**.

4.  Nella pagina **subnet** fare clic sulla subnet che si vuole modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  Nella pagina **modifica subnet** è possibile modificare la maschera di posizione, il sito di rete associato o la descrizione. Se modifichi la maschera di base, tieni presente che l'ID subnet deve essere il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet.

7.  Fare clic su **Commit**.

## <a name="delete-network-subnets"></a>Eliminare subnet di rete

Per eliminare una subnet, è possibile usare la procedura seguente. Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare una subnet di rete. 

Nella maggior parte delle distribuzioni di Skype for Business Server in cui viene implementato il controllo di ammissione di chiamata (CAC), in genere ci sarà un numero elevato di subnet. Per questo motivo, è spesso consigliabile configurare subnet da Skype for Business Server Management Shell. Da lì è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet di Windows PowerShell **Import-CSV**. Usando questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (CSV) e creare più subnet contemporaneamente. Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).


### <a name="to-delete-a-network-subnet"></a>Per eliminare una subnet di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi fare clic su **Subnet**.

4.  Nella pagina **subnet** fare clic sulla subnet che si desidera eliminare.
 
    > [!NOTE]  
    > Puoi eliminare più di una subnet alla volta. A questo scopo, premere CTRL e selezionare più subnet tenendo premuto CTRL. In alternativa, per selezionare tutte le subnet, fare clic su **Seleziona tutto** dal menu **modifica** .

5.  Scegliere **Elimina**dal menu **modifica** .

6.  Fare clic su **OK**.


## <a name="see-also"></a>Vedere anche

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
