---
title: Spostare utenti ed endpoint nel cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Spostare utenti ed endpoint prima di rimuovere le autorizzazioni di un ambiente locale di Skype for Business.
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593909"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a>Spostare gli utenti e gli endpoint necessari prima di rimuovere le autorizzazioni dell'ambiente locale

Questo articolo descrive come spostare gli utenti e gli endpoint dell'applicazione necessari nel cloud Microsoft prima di rimuovere le autorizzazioni dell'ambiente Skype for Business locale. Questo è il passaggio 1 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:

- **Passaggio 1. Spostare tutti gli utenti e gli endpoint dell'applicazione necessari da locale a online.** (Questo articolo.

- Passaggio 2. [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).

- Passaggio 3. Rimuovere la distribuzione locale di [Skype for Business.](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Spostare tutti gli utenti necessari dall'ambiente locale al cloud

Tutti gli utenti che continueranno a utilizzare dopo aver completato la migrazione devono prima essere spostati dall'ambiente locale al cloud. Gli utenti vengono spostati utilizzando gli strumenti di amministrazione locali. Per informazioni dettagliate, vedere [Move users between on-premises and cloud.](move-users-between-on-premises-and-cloud.md)

Sebbene sia possibile per gli utenti con account Skype for Business Server locali utilizzare Teams, questi utenti non dispongono delle funzionalità complete di Teams. Questi utenti non possono interagire o federatire con altri utenti che usano ancora Skype for Business (online o locale). Né questi utenti possono ricevere chiamate PSTN nel client Teams. Pertanto, è necessario spostare questi utenti online. Questo passaggio garantisce inoltre che tutti i contatti o le riunioni creati in Skype for Business Server siano migrati in Teams.

Per verificare se nella distribuzione locale sono presenti utenti rimanenti, eseguire il cmdlet seguente in una finestra di PowerShell di Skype for Business Server.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Se vengono restituiti utenti, esaminare l'output per determinare se gli account devono essere spostati nel cloud e, per tali utenti, attenersi alla procedura [riportata di seguito.](move-users-between-on-premises-and-cloud.md) Per gli account utente che non sono più necessari, eseguire il cmdlet di PowerShell di Skype for Business Server seguente:

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> L'Disable-CsUser rimuoverà tutti gli attributi di Skype for Business per tutti gli utenti che soddisfano i criteri di filtro. Prima di procedere, verificare che questi account non siano più necessari in futuro.

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a>Spostare gli endpoint dell'applicazione ibrida locale in Microsoft 365

1. Recuperare ed esportare le impostazioni dell'endpoint dell'applicazione ibrida locale eseguendo il comando di PowerShell di Skype for Business Server locale seguente:

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. Creare e creare nuove [licenze per i](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) nuovi account delle risorse in Microsoft 365 per sostituire gli endpoint dell'applicazione ibrida locale esistenti.

3. Associare i nuovi account delle risorse agli endpoint dell'applicazione ibrida esistenti.

4. Rimuovere i numeri di telefono definiti negli endpoint dell'applicazione ibrida locale eseguendo il comando di PowerShell di Skype for Business Server locale seguente:

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. Poiché è possibile che i numeri di telefono per questi account sono stati gestiti in Microsoft 365 anziché in locale, eseguire il comando seguente in PowerShell di Skype for Business online:

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. Assegnare numeri di telefono ai nuovi account delle risorse creati nel passaggio 2. Per ulteriori informazioni su come assegnare un numero di telefono a un account della risorsa, vedere l'articolo seguente: [Assegnare un numero di servizio](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).

7. Eliminare gli endpoint locali eseguendo il seguente comando di PowerShell di Skype for Business Server locale:

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
A questo punto è possibile [disabilitare la configurazione ibrida.](cloud-consolidation-disabling-hybrid.md)

## <a name="see-also"></a>Vedere anche

- [Rimuovere le autorizzazioni dell'ambiente Skype for Business locale](decommission-on-prem-overview.md)

- [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md)

- [Rimuovere la distribuzione locale di Skype for Business](decommission-remove-on-prem.md)




