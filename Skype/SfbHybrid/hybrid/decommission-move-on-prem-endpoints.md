---
title: Eseguire la migrazione degli endpoint dell'applicazione ibrida nel cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Eseguire la migrazione degli endpoint dell'applicazione hyrid prima di rimuovere le autorizzazioni Skype for Business'ambiente locale.
ms.openlocfilehash: 74e0ef935c993f6e39b08759d3beb69e0c5c7673
ms.sourcegitcommit: d8dba15c520de3894d1781e17acb2c75fb38ed49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2022
ms.locfileid: "62921854"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>Eseguire la migrazione degli endpoint dell'applicazione ibrida prima di rimuovere le autorizzazioni dell'ambiente locale

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In questo articolo viene descritto come spostare gli endpoint dell'applicazione ibrida necessari nel cloud Microsoft prima di rimuovere le autorizzazioni dell'ambiente Skype for Business locale. Questo è il passaggio 3 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:

- Passaggio 1. [Spostare tutti gli utenti necessari da locale a online](decommission-move-on-prem-users.md)

- Passaggio 2. [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).

- **Passaggio 3. Eseguire la migrazione degli endpoint dell'applicazione ibrida da locale a online.** (Questo articolo)

- Passaggio 4. [Rimuovere la distribuzione locale Skype for Business locale](decommission-remove-on-prem.md).


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>Eseguire la migrazione di tutti gli endpoint dell'applicazione ibrida necessari da locale a online

Prima di poter spostare questi endpoint in linea, è necessario assicurarsi di aver aggiornato i record DNS in modo che puntino a Microsoft 365 per tutti i domini sip utilizzati dagli endpoint. Tenere presente che una volta aggiornato IL DNS in modo che punti a Microsoft 365, tutti gli endpoint dell'applicazione ibrida esistenti non saranno più individuabili fino al completamento di questo passaggio. Poiché questo passaggio (creazione di account delle risorse online) non è possibile se i record DNS puntano a locali, è consigliabile pianificare entrambi i passaggi 2 e 3 nella stessa finestra di manutenzione. Per ulteriori informazioni, vedere [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).

1. Recuperare ed esportare le impostazioni degli endpoint dell'applicazione ibrida locale eseguendo il comando di PowerShell Skype for Business Server locale seguente:

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. Creare e creare nuove [licenze per](/microsoftteams/manage-resource-accounts) i nuovi account Microsoft 365 per sostituire gli endpoint dell'applicazione ibrida locale esistenti.

3. Associare i nuovi account delle risorse agli endpoint dell'applicazione ibrida esistenti.

4. Rimuovere i numeri di telefono definiti negli endpoint dell'applicazione ibrida locale eseguendo il comando di PowerShell Skype for Business Server locale seguente:

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. Poiché è possibile che i numeri di telefono per questi account sono stati gestiti in Microsoft 365 anziché in locale, eseguire il comando seguente in Teams PowerShell:

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

6. Assegnare numeri di telefono ai nuovi account delle risorse creati nel passaggio 2. Per ulteriori informazioni su come assegnare un numero di telefono a un account di risorsa, vedere l'articolo seguente: [Assegnare un numero di servizio](/microsoftteams/manage-resource-accounts).

7. Eliminare gli endpoint locali eseguendo il comando di PowerShell Skype for Business Server locale seguente:

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
A questo punto è possibile [rimuovere la distribuzione Skype for Business locale](decommission-remove-on-prem.md).

## <a name="see-also"></a>Vedere anche

- [Rimuovi le autorizzazioni dell'ambiente locale Skype for Business](decommission-on-prem-overview.md)

- [Spostare tutti gli utenti necessari da locale a online](decommission-move-on-prem-users.md)

- [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md)

- [Rimuovere la distribuzione locale di Skype for Business](decommission-remove-on-prem.md)

- [Creare un operatore automatico tramite cmdlet](/microsoftteams/create-a-phone-system-auto-attendant-via-cmdlets)




