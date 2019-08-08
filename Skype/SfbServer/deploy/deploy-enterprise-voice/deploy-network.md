---
title: Distribuire aree di rete, siti e subnet in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Creare o modificare aree di rete, siti di rete e associare subnet di rete in Skype for Business Server. Tutti questi elementi vengono usati per le funzionalità vocali avanzate di Enterprise: bypass multimediale, controllo di ammissione alle chiamate e routing basato sulla posizione.'
ms.openlocfilehash: 237720373c78bcb4a3cb3ad0aed376f2dc136a71
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245769"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>Distribuire aree di rete, siti e subnet in Skype for business

Creare o modificare aree di rete, siti di rete e associare subnet di rete in Skype for Business Server. Tutti questi elementi vengono usati per le funzionalità vocali avanzate di Enterprise: bypass multimediale, controllo di ammissione alle chiamate e routing basato sulla posizione.

Le funzionalità vocali avanzate per l'organizzazione sono [controllo di ammissione delle chiamate](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [bypass multimediale](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [routing basato sulla posizione](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)e [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md). Queste funzionalità richiedono tutte la creazione di aree di rete, siti di rete e subnet. Ad esempio, tutte queste funzionalità richiedono che ogni subnet della topologia sia associata a un sito di rete specifico e ogni sito di rete debba essere associato a un'area di rete. Per altre informazioni su questi termini, vedere [impostazioni di rete per le funzionalità vocali avanzate di VoIP aziendale in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).

Il controllo di ammissione alle chiamate e il E9-1-1 hanno requisiti di configurazione aggiuntivi per i siti di rete:

- Il controllo di ammissione alle chiamate richiede che venga specificato un profilo dei criteri di larghezza di banda per ogni sito vincolato dalle limitazioni della larghezza di banda WAN. Se si prevede di distribuire il controllo di ammissione di chiamata, è necessario [creare profili dei criteri di larghezza di banda in Skype for Business Server](create-bandwidth-policy-profiles.md) prima di configurare i siti di rete.

- E9-1-1 richiede l'impostazione di un criterio di posizione per ogni sito. Se si prevede di distribuire E9-1-1, è necessario [creare criteri di posizione in Skype for Business Server prima di](create-location-policies.md) configurare i siti di rete.

## <a name="create-or-modify-a-network-region"></a>Creare o modificare un'area di rete

Se sono già state create aree di rete per una di queste funzionalità, non è necessario creare nuove aree di rete. altre funzionalità vocali avanzate di Enterprise useranno le stesse aree di rete.

Può tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche delle caratteristiche. Ad esempio, se sono state create aree di rete per E9-1-1 (che non richiedono un sito centrale associato) e quindi si distribuisce il controllo di ammissione delle chiamate, è necessario modificare le definizioni dell'area di rete per specificare un sito centrale.

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>Per creare un'area di rete con Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Eseguire il cmdlet New-CsNetworkRegion per creare aree di rete:

   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Ad esempio:

   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    In questo esempio è stata creata un'area di rete denominata "NorthAmerica" associata a un sito centrale con ID sito di CHICAGO.

3. Per completare la creazione di aree di rete per la topologia, ripetere il passaggio 2 con le impostazioni per ogni area di rete.

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>Per creare un'area di rete tramite il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.

3. Fare clic su **area geografica**.

4. Fare clic su **nuovo**.

5. Nella pagina **nuova area** fare clic su **nome** e quindi digitare un nome per l'area di rete.

6. Fare clic su **sito centrale**e quindi su un sito centrale nell'elenco.

7. Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere questo sito di rete.

8. Fare clic su **Commit**.

9. Per completare la creazione di aree di rete per la topologia, ripetere i passaggi da 4 a 8 con le impostazioni per altre aree geografiche.

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>Per modificare un'area di rete con Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Eseguire il cmdlet Set-CsNetworkRegion per modificare un'area di rete esistente:

   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Ad esempio:

   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    In questo esempio è stata modificata un'area di rete esistente denominata "NorthAmerica" (creata usando le procedure descritte più indietro in questo argomento) modificando la descrizione. Se esiste una descrizione per l'area "NorthAmerica", questo comando lo sovrascrive con questo valore; Se non è stata impostata alcuna descrizione, questo comando lo imposta.

3. Per modificare altre aree di rete, ripetere il passaggio 2 con le impostazioni per altre aree geografiche.

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>Per modificare un'area di rete tramite il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.

3. Fare clic sul pulsante di spostamento dell' **area geografica** .

4. Nella tabella fare clic sull'area di rete che si vuole modificare.

5. Fare clic su **modifica**e quindi su **Mostra dettagli.**

6. Nella pagina **Edit Region** modificare i valori delle impostazioni dell'area di rete in base alle esigenze.

7. Fare clic su **Commit**.

8. Per completare la modifica delle aree di rete, ripetere i passaggi da 4 a 7 con le impostazioni per altre aree geografiche.

## <a name="create-or-modify-a-network-site"></a>Creare o modificare un sito di rete

Se sono già stati creati siti di rete per una di queste funzionalità, non è necessario creare nuovi siti di rete. altre funzionalità vocali avanzate di Enterprise useranno gli stessi siti di rete. Può tuttavia essere necessario modificare una definizione di sito di rete esistente per applicare impostazioni specifiche delle caratteristiche. Se ad esempio è stato creato un sito di rete per E9-1-1, è necessario modificare il sito di rete durante la distribuzione del controllo di ammissione delle chiamate per applicare un profilo dei criteri di larghezza di banda.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>Per creare un sito di rete usando Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Eseguire il cmdlet New-CsNetworkSite per creare siti di rete:

   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    Ad esempio:

   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    In questo esempio è stato creato un sito di rete denominato "Chicago" che si trova nell'area di rete "NorthAmerica".

    > [!NOTE]
    > L'area di rete NorthAmerica deve esistere già affinché il comando venga eseguito correttamente.

3. Per completare la creazione di siti di rete per la topologia, ripetere il passaggio 2 con le impostazioni per altri siti.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>Per creare un sito di rete usando il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.

3. Fare clic sul pulsante di spostamento del **sito** .

4. Fare clic su **nuovo**.

5. Nella pagina **nuovo sito** fare clic su **nome** e quindi digitare un nome per il sito di rete.

6. Fare clic su **area geografica**e quindi fare clic su un'area nell'elenco.

7. Facoltativamente, fare clic su **criteri di larghezza di banda**e quindi fare clic su un criterio di larghezza di banda nell'elenco.

    > [!NOTE]
    > I criteri di larghezza di banda sono necessari solo se si distribuisce il controllo di ammissione delle chiamate nel sito.

8. Facoltativamente, fare clic su **criteri posizione**e quindi fare clic su un criterio di posizione nell'elenco.

    > [!NOTE]
    > I criteri di posizione sono necessari solo se si distribuisce E9-1-1 nel sito.

9. Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere questo sito di rete.

10. Fare clic su **Commit**.

11. Per completare la creazione di siti di rete per la topologia, ripetere i passaggi da 4 a 10 con le impostazioni per altri siti.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>Per modificare un sito di rete tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Eseguire il cmdlet Set-CsNetworkSite per modificare i siti di rete:

   ```
   Set-CsNetworkSite -Identity <string>
   ```

    Ad esempio:

   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    In questo esempio, il sito denominato "Albuquerque" viene spostato nell'area di rete "NorthAmerica". Per modificare la configurazione del sito di rete per distribuire il controllo di ammissione alle chiamate, E9-1-1 o bypass multimediale, modificare le impostazioni del sito di rete eseguendo il cmdlet Set-CsNetworkSite rispettivamente con il parametro BWPolicyProfileID o LocationPolicy.

    > [!NOTE]
    > Anche se il parametro BypassID esiste per il bypass multimediale, ti consigliamo vivamente di non eseguire l'override degli ID di bypass generati automaticamente. Non è necessario specificare parametri aggiuntivi per configurare un sito di rete per il bypass multimediale.

3. Per completare la modifica dei siti di rete per la topologia, ripetere il passaggio 2 con le impostazioni per altri siti.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>Per modificare un sito di rete tramite il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.

3. Fare clic sul pulsante di spostamento del **sito** .

4. Nella tabella fare clic sul sito di rete che si desidera modificare.

5. Fare clic su **modifica**e quindi su **Mostra dettagli.**

6. Nella pagina **modifica sito** modificare i valori delle impostazioni del sito di rete in base alle esigenze.

7. Fare clic su **Commit**.

8. Per completare la modifica dei siti di rete, ripetere i passaggi da 4 a 7 con le impostazioni per altri siti.

## <a name="associate-a-subnet-with-a-network-site"></a>Associare una subnet a un sito di rete
<a name="BKMK_AssociateSubnets"> </a>

Ogni subnet della rete deve essere associata a un sito di rete specifico, poiché le informazioni di subnet vengono usate per determinare il sito di rete in cui si trova un endpoint mentre viene avviata una nuova sessione. Quando si conosce la posizione di ogni parte di una sessione, le funzionalità vocali avanzate di Enterprise possono applicare tali informazioni per determinare come gestire la configurazione o il routing delle chiamate.

Tutti gli indirizzi IP pubblici configurati per i server Edge audio/video nella distribuzione devono essere aggiunti alle impostazioni di configurazione della rete. Questi indirizzi IP vengono aggiunti come subnet con una maschera di 32. Il sito di rete associato deve corrispondere al sito di rete configurato appropriato. Ad esempio, l'indirizzo IP pubblico che corrisponde al servizio a/V Edge nel sito centrale di Chicago sarebbe NetworkSiteID Chicago.

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>Per associare una subnet a un sito di rete tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Eseguire il cmdlet **New-CsNetworkSubnet** per associare una subnet a un sito di rete:

   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    Ad esempio:

   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    In questo esempio è stata creata un'associazione tra la subnet 172.11.12.13 e il sito di rete "Chicago".

3. Ripetere il passaggio 2 per tutte le subnet della topologia.

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>Per associare subnet a siti di rete mediante l'importazione di un file CSV

1. Creare un file CSV che includa tutte le subnet che si desidera aggiungere. Ad esempio, crea un file denominato **subnet. csv** con il contenuto seguente:

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

3. Eseguire il cmdlet seguente per importare **subnet. csv**e quindi archiviarne il contenuto in Lync Server Management store:

   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>Per associare una subnet a un sito di rete tramite il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.

3. Fare clic sul pulsante di spostamento **subnet** .

4. Fare clic su **nuovo**.

5. Nella pagina **nuova subnet** fare clic su **ID Subnet**e quindi digitare il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet che si vuole associare a un sito di rete.

6. Fare clic su **maschera**e quindi digitare la maschera di forma da applicare alla subnet.

7. Fare clic su **ID sito di rete**e quindi selezionare l'ID sito del sito a cui si sta aggiungendo la subnet.

    > [!NOTE]
    > Se non sono ancora stati creati siti di rete, l'elenco sarà vuoto. Per informazioni dettagliate sulla procedura, vedere [creare o modificare un sito di rete](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx). È anche possibile recuperare gli ID sito per la distribuzione eseguendo il cmdlet **Get-CsNetworkSite** . Per informazioni dettagliate, vedi la documentazione di Skype for Business Server Management Shell.

8. Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere la subnet.

9. Fare clic su **Commit**.

Ripetere questi passaggi per aggiungere altre subnet a un sito di rete.
> [!NOTE]
> Viene generato un avviso KHI (Key Health Indicator), che specifica un elenco di indirizzi IP presenti nella rete, ma che non sono associati a una subnet oppure che la subnet che include gli indirizzi IP non è associata a un sito di rete. Questo avviso non verrà generato più di una volta all'interno di un periodo di 8 ore.

Di seguito sono riportate le informazioni relative agli avvisi e un esempio:

 **Origine**: CS Bandwidth Policy Service (Core)

 **Numero evento**: 36034

 **Livello**: 2

 **Descrizione**: le subnet per gli indirizzi IP seguenti: \<l'elenco di indirizzi\> IP non è configurato o le subnet non sono associate a un sito di rete.

 **Causa**: le subnet per gli indirizzi IP corrispondenti mancano alle impostazioni di configurazione della rete o le subnet non sono associate a un sito di rete.

 **Risoluzione**: aggiungere subnet che corrispondono all'elenco di indirizzi IP nelle impostazioni di configurazione della rete e associare ogni subnet a un sito di rete.

Ad esempio, se l'elenco di indirizzi IP nell'avviso specifica 10.121.248.226 e 10.121.249.20, questi indirizzi IP non sono associati a una subnet o la subnet a cui sono associati non appartiene a un sito di rete. Se 10.121.248.0/24 e 10.121.249.0/24 sono le subnet corrispondenti per questi indirizzi, è possibile risolvere il problema come segue:

1. Assicurarsi che l'indirizzo IP 10.121.248.226 sia associato alla subnet 10.121.248.0/24 e l'indirizzo IP 10.121.249.20 sia associato alla subnet 10.121.249.0/24.

2. Assicurarsi che le subnet 10.121.248.0/24 e 10.121.249.0/24 siano associate a un sito di rete.

## <a name="see-also"></a>Vedere anche
<a name="BKMK_AssociateSubnets"> </a>


[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

