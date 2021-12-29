---
title: Usare PowerShell per le attività nel menu Configurazione di rete
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Riepilogo: Skype for Business Server pannello di controllo al mapping cmdlet per il menu Configurazione di rete.'
ms.openlocfilehash: aa42ac465ffd72a4aff9c03293124c857e5b712c
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626304"
---
# <a name="network-configuration"></a>Configurazione di rete

In questo articolo viene descritto come ottenere risultati simili a quelli della voce di **menu** Configurazione di rete nel Pannello di controllo legacy utilizzando i cmdlet.

In questo articolo vengono descritti i sottomenu seguenti:

- [Configurazione di rete](#network-configuration)
  - [Criteri percorso](#location-policy)
  - [Criteri larghezza di banda](#bandwidth-policy)
  - [Area](#region)
  - [Site](#site)
  - [Subnet](#subnet)
  - [Collegamento area geografica](#region-link)
  - [Route area geografica](#region-route)

## <a name="location-policy"></a>Criteri percorso

Il **sottomenu CRITERI** PERCORSO viene utilizzato per applicare impostazioni correlate alla funzionalità E9-1-1. I criteri di posizione determinano se un utente è abilitato per E9-1-1 e in questo caso il funzionamento di una chiamata di emergenza.

Prendere in considerazione le varie attività che un utente può eseguire in **CRITERI** PERCORSO e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutti i criteri percorso

   ![Criteri percorso elenco](./media/location-policy-1.png)

***Cmdlet***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***Esempio***

```powershell
 Get-CsLocationPolicy
```

---

> **Scenario 2:** creare un nuovo criterio percorso

   ![Creare criteri percorso](./media/location-policy-2.png)

***Cmdlet***

[New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy)  

***Esempio***

```powershell
 New-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

> **Scenario 3:** ottenere i dettagli di un criterio percorso scelto

   ![Ottenere criteri percorso](./media/location-policy-3.png)

***Cmdlet***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***Esempio***

```powershell
 Get-CsLocationPolicy -Identity Reno
```

---

> **Scenario 4**: Eliminare i criteri percorso scelti

   ![Elimina criteri percorso](./media/location-policy-4.png)

***Cmdlet***

[Remove-CsLocationPolicy](/powershell/module/skype/remove-cslocationpolicy)

***Esempio***

```powershell
 Remove-CsLocationPolicy -Identity Reno
```

---

> **Scenario 5:** aggiornare un criterio percorso

   ![Aggiornare i criteri percorso](./media/location-policy-5.png)

***Cmdlet***

[Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy)

***Esempio***

```powershell
 Set-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

## <a name="bandwidth-policy"></a>Criteri larghezza di banda

In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità. (In Skype for Business Server, solo le modalità audio e video possono essere assegnate limitazioni di larghezza di banda. Questo cmdlet crea un profilo contenitore per questi criteri. Definire i singoli criteri nel contenitore specificando le limitazioni della larghezza di banda audio e video quando si chiama il cmdlet.

Prendere in considerazione le varie attività che un utente può eseguire in **CRITERI** DI LARGHEZZA DI BANDA e i cmdlet Skype for Business a cui tali attività sono mappate.

---
> **Scenario 1:** elencare tutti i criteri di larghezza di banda

   ![Criteri larghezza di banda elenco](./media/bandwidth-policy-1.png)

***Cmdlet***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***Esempio***

```powershell
 Get-CsNetworkBandwidthPolicyProfile
```

---

> **Scenario 2:** creare un nuovo criterio di larghezza di banda

   ![Nuovo criterio larghezza di banda](./media/bandwidth-policy-2.png)

***Cmdlet***

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile)  

***Esempio***

```powershell
 New-CsNetworkBandwidthPolicyProfile -Identity LowBWLimits -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400 -VideoBWSessionLimit 500
```

---

> **Scenario 3:** ottenere i dettagli di un criterio di larghezza di banda scelto

   ![Ottenere i criteri di larghezza di banda](./media/bandwidth-policy-3.png)

***Cmdlet***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***Esempio***

```powershell
 Get-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **Scenario 4**: Eliminare i criteri di larghezza di banda scelti

   ![Elimina criteri larghezza di banda](./media/bandwidth-policy-4.png)

***Cmdlet***

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile)

***Esempio***

```powershell
 Remove-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **Scenario 5:** aggiornare un criterio di larghezza di banda

   ![Aggiornare i criteri di larghezza di banda](./media/bandwidth-policy-5.png)

***Cmdlet***

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile)

***Esempio***

```powershell
 Set-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -VideoBWLimit 2500 -VideoBWSessionLimit 300
```

---

## <a name="region"></a>Area geografica

Un'area di rete interconnette diverse parti di una rete dislocate su più aree geografiche. Ogni area di rete deve essere associata a un sito centrale. Gli amministratori possono utilizzare il menu **REGION** per gestire le informazioni su una o più aree di rete, inclusi il sito centrale associato e le impostazioni che determinano se sono consentiti percorsi alternativi per le connessioni audio e video e che associano i siti all'interno dell'area a una configurazione di bypass multimediale.

---

> **Scenario 1:** elencare tutte le aree geografiche

   ![Area elenco](./media/network-region-1.png)

***Cmdlet***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***Esempio***

```powershell
 Get-CsNetworkRegion
```

---

> **Scenario 2:** creare una nuova area geografica

   ![Crea area geografica](./media/network-region-2.png)

***Cmdlet***

[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion)  

***Esempio***

```powershell
 New-CsNetworkRegion -Identity NorthAmerica -Description "All North American Locations" -CentralSite Redmond-NA-MLS
```

---

> **Scenario 3:** ottenere i dettagli di un'area scelta

   ![Ottieni area geografica](./media/network-region-3.png)

***Cmdlet***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***Esempio***

```powershell
 Get-CsNetworkRegion -Identity NorthAmerica
```

---

> **Scenario 4**: Eliminare le aree selezionate

   ![Elimina area](./media/network-region-4.png)

***Cmdlet***

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion)

***Esempio***

```powershell
 Remove-CsNetworkRegion -Identity NorthAmerica
```

---

> **Scenario 5:** aggiornare un'area geografica

   ![Area di aggiornamento](./media/network-region-5.png)

- **Annotazione 1 - Risultato**

    Questa annotazione sull'immagine indica un risultato, cio? i dati recuperati e visualizzati.

    ***Cmdlet***

    [Get-CsNetworkSite dall'area geografica](/powershell/module/skype/get-csnetworksite)

    ***Esempio***

    ```powershell
     Get-CsNetworkSite | Where-Object {$_.NetworkRegionID -eq "AKR"}
    ```

- **Annotazione 2 - Opzione (per l'utente)**

    Questa annotazione sull'immagine indica un'opzione che l'utente può implementare, cio? per salvare un'area di rete.

    [Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion)

   ***Esempio***

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -Description "North American Region"
   ```

---

## <a name="site"></a>Sito

I siti di rete sono gli uffici o le postazioni configurati in ogni regione di una distribuzione CAC o per le chiamate di emergenza. **Il** sottomenu SITE consente agli amministratori di aggiungere, rimuovere o gestire le impostazioni.

Prendere in considerazione le varie attività che un utente può eseguire in **SITE** e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutti i siti

   ![Sito elenco](./media/network-site-1.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***Esempio***

```powershell
 Get-CsNetworkSite
```

---

> **Scenario 2**: Creare un nuovo sito

   ![Crea sito](./media/network-site-2.png)

***Cmdlet***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksite)  

***Esempio***

```powershell
 New-CsNetworkSite -Identity Vancouver -NetworkRegionID NorthAmerica
```

---

> **Scenario 3:** ottenere i dettagli di un sito scelto

   ![Ottieni sito](./media/network-site-3.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***Esempio***

```powershell
 Get-CsNetworkSite -Identity Redmond
```

---

> **Scenario 4**: Eliminare i siti scelti

   ![Elimina sito](./media/network-site-4.png)

***Cmdlet***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksite)

***Esempio***

```powershell
 Remove-CsNetworkSite -Identity Vancouver
```

---

> **Scenario 5:** aggiornare un sito

   ![Aggiorna sito](./media/network-site-5.png)

- **Annotazione 1 - Risultato**

    Questa annotazione sull'immagine indica un risultato, cio? i dati recuperati e visualizzati.

    ***Cmdlet***

    [Get-CsNetworkSubnet dal sito](/powershell/module/skype/get-csnetworksubnet)

    ***Esempio***

    ```powershell
     Get-CsNetworkSubnet | Where-Object {$_.NetworkSiteID -eq "Vancouver"}
    ```

- **Annotazione 2 - Opzione (per l'utente)**

    Questa annotazione sull'immagine indica un'opzione che l'utente può implementare, cio? per salvare un sito di rete.

   ***Cmdlet***

   [Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksite)

   ***Esempio***

   ```powershell
    Set-CsNetworkSite -Identity Vancouver - BWPolicyProfileID LowBWLimits
   ```

---

## <a name="subnet"></a>Subnet

Gli amministratori possono utilizzare il sottomenu **SUBNET** per creare, aggiornare e gestire subnet di rete.

Prendere in considerazione le varie attività che un utente può eseguire su **SUBNET** e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutte le subnet

   ![Subnet elenco](./media/network-subnet-1.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***Esempio***

```powershell
 Get-CsNetworkSubnet
```

---

> **Scenario 2:** creare una nuova subnet

   ![Creare subnet](./media/network-subnet-2.png)

***Cmdlet***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet)  

***Esempio***

```powershell
 New-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 24 -NetworkSiteID Vancouver
```

---

> **Scenario 3:** ottenere i dettagli di una subnet scelta

   ![Get Subnet](./media/network-subnet-3.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***Esempio***

```powershell
 Get-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **Scenario 4**: Eliminare le subnet scelte

   ![Elimina subnet](./media/network-subnet-4.png)

***Cmdlet***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet)

***Esempio***

```powershell
 Remove-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **Scenario 5:** aggiornare una subnet

   ![Aggiorna subnet](./media/network-subnet-5.png)

***Cmdlet***

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet)

***Esempio***

```powershell
 Set-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 25 -NetworkSiteID Chicago
```

---

## <a name="region-link"></a>Collegamento area geografica

Le aree all'interno di una rete sono collegate tramite connettività WAN fisica. Gli amministratori possono utilizzare il sottomenu **COLLEGAMENTO** AREA per creare, aggiornare e gestire subnet di rete.

Prendiamo in considerazione le varie attività che un utente può eseguire in **REGION LINK** e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutti i collegamenti di area geografica

   ![Collegamento area elenco](./media/network-regionlink-1.png)

***Cmdlet***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***Esempio***

```powershell
 Get-CsNetworkRegionLink
```

---

> **Scenario 2:** creare un nuovo collegamento area geografica

   ![Crea collegamento area](./media/network-regionlink-2.png)

***Cmdlet***

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionLink)  

***Esempio***

```powershell
 New-CsNetworkRegionLink -Identity NA_EMEA -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID LowBWLimits
```

---

> **Scenario 3:** ottenere i dettagli di un collegamento area scelta

   ![Ottieni collegamento area geografica](./media/network-regionlink-3.png)

***Cmdlet***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***Esempio***

```powershell
 Get-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **Scenario 4**: Eliminare i collegamenti di area geografica selezionati

   ![Elimina collegamento area](./media/network-regionlink-4.png)

***Cmdlet***

[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionLink)

***Esempio***

```powershell
 Remove-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **Scenario 5:** aggiornare un collegamento area geografica

   ![Aggiorna collegamento area](./media/network-regionlink-5.png)

***Cmdlet***

[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionLink)

***Esempio***

```powershell
 Set-CsNetworkRegionLink -Identity NA_EMEA -BWPolicyProfileID HighBWLimits
```

---

## <a name="region-route"></a>Route area geografica

Ciascuna regione entro una configurazione CAC deve avere la possibilità di accedere a tutte le altre regioni. Mentre i collegamenti tra regioni impostano delle limitazione alla larghezza di banda nelle connessioni e rappresentano anche un collegamento fisico, una route stabilisce attraverso quale percorso collegato passerà la connessione da una regione all'altra. Gli amministratori possono utilizzare il sottomenu **ROUTE** AREA per crearne, aggiornarne e gestirne la gestione.

Prendiamo in considerazione le varie attività che un utente può eseguire in **ROUTE** REGION e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutte le route dell'area geografica

   ![Route area elenco](./media/network-regionroute-1.png)

***Cmdlet***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***Esempio***

```powershell
 Get-CsNetworkInterRegionRoute
```

---

> **Scenario 2:** creare una nuova route area geografica

   ![Crea route area](./media/network-regionroute-2.png)

***Cmdlet***

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute)  

***Esempio***

```powershell
 New-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA_EMEA,EMEA_APAC"
```

---

> **Scenario 3:** ottenere i dettagli di una route area scelta

   ![Ottieni route area geografica](./media/network-regionroute-3.png)

***Cmdlet***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***Esempio***

```powershell
 Get-CsNetworkInterRegionRoute -Filter *APAC*
```

---

> **Scenario 4**: Eliminare le route di area geografica scelte

   ![Elimina route area](./media/network-regionroute-4.png)

***Cmdlet***

[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute)

***Esempio***

```powershell
 Remove-CsNetworkInterRegionRoute -Identity NA_APAC_Route
```

---

> **Scenario 5:** aggiornare una route area geografica

   ![Aggiorna route area](./media/network-regionroute-5.png)

- **Annotazione 1 - Opzione (per l'utente)**

    Questa annotazione sull'immagine indica un risultato, cio? i dati recuperati e visualizzati.

   ***Cmdlet***

   [Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

   ***Esempio***

   ```powershell
   Get-CsNetworkRegionLink
   ```

- **Annotazione 2 - Opzione (per l'utente)**

    Questa annotazione sull'immagine indica un'opzione che l'utente può implementare, cio? per salvare una route dell'area di rete.

    ***Cmdlet***

   [Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute)

   ***Esempio***

   ```powershell
   Set-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionLinkIDs "NA_SA,SA_APAC"
   ```

---
---
