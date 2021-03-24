---
title: Distribuire aree di rete, siti e subnet in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Creare o modificare aree di rete, siti di rete e associare subnet di rete in Skype for Business Server. Tutte queste funzionalità vengono utilizzate per le funzionalità VoIP aziendale avanzate: bypass multimediale, controllo di ammissione di chiamata e routing basato sulla posizione.'
ms.openlocfilehash: adfcf418fd2b1ef607947687afb766fee6b64715
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103522"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>Distribuire aree di rete, siti e subnet in Skype for Business

Creare o modificare aree di rete, siti di rete e associare subnet di rete in Skype for Business Server. Tutte queste funzionalità vengono utilizzate per le funzionalità VoIP aziendale avanzate: bypass multimediale, controllo di ammissione di chiamata e routing basato sulla posizione.

Le funzionalità VoIP aziendale avanzate [sono](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)controllo di ammissione di chiamata, [bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)multimediale, [routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)basato sulla posizione ed [E9-1-1.](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md) Tutte queste funzionalità richiedono la creazione di aree di rete, siti di rete e subnet. Ad esempio, tutte queste funzionalità richiedono che ogni subnet della topologia sia associata a un sito di rete specifico e che ogni sito di rete sia associato a un'area di rete. Per ulteriori informazioni su questi termini, vedere Impostazioni di [rete per le funzionalità VoIP aziendale avanzate in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)

Per il controllo di ammissione di chiamata e il servizio E9-1-1 sono previsti ulteriori requisiti di configurazione per i siti di rete:

- Per il controllo di ammissione di chiamata è necessario specificare un profilo di criteri di larghezza di banda per ogni sito vincolato da limitazioni della larghezza di banda WAN. Se si prevede di distribuire il controllo di ammissione di chiamata, è necessario creare profili dei criteri di larghezza di [banda in Skype for Business Server](create-bandwidth-policy-profiles.md) prima di configurare i siti di rete.

- Per il servizio E9-1-1 è necessario specificare criteri di percorso per ogni sito. Se si prevede di distribuire E9-1-1, è necessario creare criteri percorso [in Skype for Business Server](create-location-policies.md) prima di configurare i siti di rete.

## <a name="create-or-modify-a-network-region"></a>Creare o modificare un'area di rete

Se sono già state create aree di rete per una di queste funzionalità, non è necessario creare nuove aree di rete. altre funzionalità VoIP aziendale utilizzeranno le stesse aree di rete.

Potrebbe tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche della caratteristica. Ad esempio, se sono state create aree di rete per E9-1-1 (che non richiedono un sito centrale associato) e quindi si distribuisce il controllo di ammissione di chiamata, è necessario modificare le definizioni delle aree di rete per specificare un sito centrale.

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>Per creare un'area di rete tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**

2. Eseguire il cmdlet New-CsNetworkRegion per creare le aree di rete:

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Ad esempio:

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    In questo esempio è stata creata un'area di rete denominata "NorthAmerica" associata a un sito centrale con ID sito CHICAGO.

3. Per completare la creazione delle aree di rete per la topologia, ripetere il passaggio 2 con le impostazioni per ogni area di rete.

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>Per creare un'area di rete tramite il Pannello di controllo di Skype for Business Server

1. Aprire il Pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.

3. Fare clic su **Area**.

4. Fare clic su **Nuovo**.

5. Nella pagina **Nuova area** fare clic su **Nome** e quindi digitare un nome per l'area di rete.

6. Fare clic su **Sito centrale** e quindi fare clic su un sito centrale nell'elenco.

7. Facoltativamente, fare clic su **Descrizione** e quindi digitare ulteriori informazioni per descrivere il sito di rete.

8. Fare clic su **Commit**.

9. Per completare la creazione delle aree di rete per la topologia, ripetere i passaggi da 4 a 8 con le impostazioni per le altre aree.

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>Per modificare un'area di rete tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**

2. Eseguire il cmdlet Set-CsNetworkRegion per modificare un'area di rete esistente:

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Ad esempio:

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    In questo esempio è stata modificata un'area di rete esistente denominata "NorthAmerica" (creata utilizzando le procedure descritte in precedenza in questo argomento) modificando la descrizione. Se esiste una descrizione per l'area "NorthAmerica", questo comando la sovrascrive con questo valore. se non è stata impostata alcuna descrizione, questo comando la imposta.

3. Per modificare altre aree di rete, ripetere il passaggio 2 con le impostazioni per le altre aree.

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>Per modificare un'area di rete tramite il Pannello di controllo di Skype for Business Server

1. Aprire il Pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.

3. Fare clic sul pulsante di spostamento **Area**.

4. Nella tabella fare clic sull'area di rete che si desidera modificare.

5. Fare clic su **Modifica** e quindi su **Mostra dettagli**.

6. Nella pagina **Modifica area** modificare i valori per le impostazioni dell'area di rete in base alle esigenze.

7. Fare clic su **Commit**.

8. Per completare la modifica delle aree di rete, ripetere i passaggi da 4 a 7 con le impostazioni per le altre aree.

## <a name="create-or-modify-a-network-site"></a>Creare o modificare un sito di rete

Se sono già stati creati siti di rete per una di queste funzionalità, non è necessario creare nuovi siti di rete. altre funzionalità VoIP aziendale utilizzeranno gli stessi siti di rete. Potrebbe tuttavia essere necessario modificare una definizione di sito di rete esistente per applicare impostazioni specifiche delle caratteristiche. Ad esempio, se è stato creato un sito di rete per E9-1-1, è necessario modificare il sito di rete durante la distribuzione del controllo di ammissione di chiamata per applicare un profilo di criteri di larghezza di banda.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>Per creare un sito di rete tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**

2. Eseguire il cmdlet New-CsNetworkSite per creare i siti di rete:

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    Ad esempio:

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    In questo esempio è stato creato un sito di rete denominato "Chicago" nell'area di rete "NorthAmerica".

    > [!NOTE]
    > Per il corretto funzionamento di questo comando, l'area di rete NorthAmerica deve esistere già.

3. Per completare la creazione dei siti di rete per la propria topologia, ripetere il passaggio 2 con le impostazioni relative agli altri siti.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>Per creare un sito di rete tramite il Pannello di controllo di Skype for Business Server

1. Aprire il Pannello di controllo di Skype for Business Server.

2. Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.

3. Fare clic sul pulsante di spostamento **Sito**.

4. Fare clic su **Nuovo**.

5. Nella pagina **Nuovo sito** fare clic su **Nome** e quindi digitare un nome per il sito di rete.

6. Fare clic su **Area** e quindi selezionare un'area nell'elenco.

7. Facoltativamente, fare clic su **Criteri larghezza di banda** e quindi selezionare un criterio larghezza di banda nell'elenco.

    > [!NOTE]
    > Il criterio larghezza di banda è necessario solo se nel sito viene distribuito il controllo di ammissione di chiamata.

8. Facoltativamente, fare clic su **Criteri percorso** e quindi selezionare un criterio percorso nell'elenco.

    > [!NOTE]
    > Il criterio percorso è necessario solo se nel sito viene distribuito il servizio E9-1-1.

9. Facoltativamente, fare clic su **Descrizione** e quindi digitare ulteriori informazioni per descrivere il sito di rete.

10. Fare clic su **Commit**.

11. Per completare la creazione dei siti di rete per la propria topologia, ripetere i passaggi da 4 a 10 con le impostazioni relative agli altri siti.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>Per modificare un sito di rete tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**

2. Eseguire il cmdlet Set-CsNetworkSite per modificare i siti di rete:

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    Ad esempio:

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    In questo esempio, il sito denominato "Albuquerque" viene spostato nell'area di rete "NorthAmerica". Per modificare la configurazione del sito di rete in modo da distribuire il controllo di ammissione di chiamata, il servizio E9-1-1 o il bypass multimediale, modificare le impostazioni del sito di rete eseguendo il cmdlet Set-CsNetworkSite rispettivamente con il parametro BWPolicyProfileID o LocationPolicy.

    > [!NOTE]
    > Anche se per il bypass multimediale esiste il parametro BypassID, è consigliabile non sostituire gli ID bypass generati automaticamente. Non è necessario specificare ulteriori parametri per configurare un sito di rete per il bypass multimediale.

3. Per completare la modifica dei siti di rete per la propria topologia, ripetere il passaggio 2 con le impostazioni relative agli altri siti.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>Per modificare un sito di rete tramite il Pannello di controllo di Skype for Business Server

1. Aprire il Pannello di controllo di Skype for Business Server.

2. Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.

3. Fare clic sul pulsante di spostamento **Sito**.

4. Nella tabella fare clic sul sito di rete che si desidera modificare.

5. Scegliere **Mostra dettagli** dal menu **Modifica**.

6. Nella pagina **Modifica sito** modificare i valori per le impostazioni del sito di rete in base alle esigenze.

7. Fare clic su **Commit**.

8. Per completare la modifica dei siti di rete, ripetere i passaggi da 4 a 7 con le impostazioni relative agli altri siti.

## <a name="associate-a-subnet-with-a-network-site"></a>Associare una subnet a un sito di rete
<a name="BKMK_AssociateSubnets"> </a>

Ogni subnet della rete deve essere associata a un sito di rete specifico, poiché le informazioni sulle subnet vengono utilizzate per determinare il sito di rete in cui si trova un endpoint durante l'avvio di una nuova sessione. Quando la posizione di ogni parte in una sessione è nota, le funzionalità VoIP aziendale avanzate possono applicare queste informazioni per determinare come gestire la configurazione o l'instradamento delle chiamate.

Tutti gli indirizzi IP pubblici configurati dei server perimetrali audio/video nella distribuzione devono essere aggiunti alle impostazioni di configurazione di rete. Questi indirizzi IP vengono aggiunti come subnet con una maschera di 32. Il sito di rete associato deve corrispondere al sito di rete configurato appropriato. Ad esempio, l'indirizzo IP pubblico corrispondente al servizio A/V Edge nel sito centrale Chicago sarà NetworkSiteID Chicago.

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>Per associare una subnet a un sito di rete tramite Skype for Business Server Management Shell

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**

2. Eseguire il cmdlet **New-CsNetworkSubnet** per associare una subnet a un sito di rete:

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    Ad esempio:

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    In questo esempio è stata creata un'associazione tra la subnet 172.11.12.13 e il sito di rete "Chicago".

3. Ripetere il passaggio 2 per tutte le subnet della topologia.

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>Per associare subnet a siti di rete importando un file CSV

1. Creare un file CSV che includa tutte le subnet che si desidera aggiungere. Ad esempio, creare un file denominato **subnet.csv** con il contenuto seguente:

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**

3. Eseguire il cmdlet seguente per importare **subnet.csv** e quindi archiviarne il contenuto nell'archivio di gestione di Lync Server:

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>Per associare una subnet a un sito di rete tramite il Pannello di controllo di Skype for Business Server

1. Aprire il Pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.

3. Fare clic sul **pulsante di** spostamento Subnet.

4. Fare clic su **Nuova regola**.

5. Nella pagina **Nuova subnet** fare clic su **ID** subnet e quindi digitare il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet che si desidera associare a un sito di rete.

6. Fare **clic su** Maschera e quindi digitare la maschera di bit da applicare alla subnet.

7. Fare **clic su ID sito** di rete e quindi selezionare l'ID sito del sito a cui si desidera aggiungere la subnet.

    > [!NOTE]
    > Se non sono ancora stati creati siti di rete, questo elenco sarà vuoto. Per informazioni dettagliate sulla procedura, vedere [Create or Modify a Network Site.](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site) È inoltre possibile recuperare gli ID sito per la distribuzione eseguendo il cmdlet **Get-CsNetworkSite.** Per informazioni dettagliate, vedere la documentazione di Skype for Business Server Management Shell.

8. Facoltativamente, fare **clic su Descrizione** e quindi digitare informazioni aggiuntive per descrivere questa subnet.

9. Fare clic su **Commit**.

Ripetere questi passaggi per aggiungere altre subnet a un sito di rete.
> [!NOTE]
> Viene generato un avviso Key Health Indicator (KHI) in cui viene specificato un elenco di indirizzi IP presenti nella rete che non sono associati a una subnet oppure la cui subnet non è associata a un sito di rete. Questo avviso non verrà generato più di una volta entro un periodo di 8 ore.

Di seguito vengono riportati un esempio e le informazioni rilevanti dell'avviso:

 **Origine**: Servizio criteri larghezza di banda LS (Core)

 **Numero evento**: 36034

 **Livello**: 2

 **Descrizione:** le subnet per i seguenti indirizzi IP: non sono configurate o le subnet non sono \<List of IP Addresses\> associate a un sito di rete.

 **Causa**: le subnet per gli indirizzi IP corrispondenti non sono presenti nelle impostazioni della configurazione di rete oppure non sono associate a un sito di rete.

 **Soluzione:** aggiungere subnet corrispondenti all'elenco di indirizzi IP nelle impostazioni di configurazione di rete e associare ogni subnet a un sito di rete.

Ad esempio, se l'elenco di indirizzi IP nell'avviso specifica 10.121.248.226 e 10.121.249.20, questi indirizzi IP non sono associati a una subnet o la subnet a cui sono associati non appartiene a un sito di rete. Se 10.121.248.0/24 e 10.121.249.0/24 sono le subnet corrispondenti per questi indirizzi, è possibile risolvere il problema in questo modo:

1. Verificare che l'indirizzo IP 10.121.248.226 sia associato alla subnet 10.121.248.0/24 e che l'indirizzo IP 10.121.249.20 sia associato alla subnet 10.121.249.0/24.

2. Verificare che le subnet 10.121.248.0/24 e 10.121.249.0/24 siano associate ognuna a un sito di rete.

## <a name="see-also"></a>Vedere anche
<a name="BKMK_AssociateSubnets"> </a>


[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)