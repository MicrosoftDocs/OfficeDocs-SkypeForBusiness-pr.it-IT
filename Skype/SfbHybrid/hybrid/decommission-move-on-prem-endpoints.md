---
title: Spostare gli endpoint dell'applicazione ibrida nel cloud
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
description: Spostare gli endpoint dell'applicazione irid prima di rimuovere le autorizzazioni di un ambiente locale di Skype for Business.
ms.openlocfilehash: af8b521eaaf4a1e86027936f3d4d3600ab4bfa7b
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656880"
---
# <a name="move-hyrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>Spostare gli endpoint dell'applicazione hyrid prima di rimuovere le autorizzazioni dell'ambiente locale

Questo articolo descrive come spostare gli endpoint dell'applicazione ibrida necessari nel cloud Microsoft prima di rimuovere le autorizzazioni dell'ambiente Skype for Business locale. Questo è il passaggio 3 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:

- Passaggio 1. [Spostare tutti gli utenti necessari da locale a online](decommission-move-on-prem-users.md)

- Passaggio 2. [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).

- **Passaggio 3. Spostare gli endpoint dell'applicazione ibrida da locale a online.** (Questo articolo)

- Passaggio 4. Rimuovere la distribuzione locale di [Skype for Business.](decommission-remove-on-prem.md)


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>Spostare tutti gli endpoint dell'applicazione ibrida necessari da locale a online

Prima di poter spostare questi endpoint in linea, è necessario assicurarsi di avere aggiornato i record DNS in modo che puntino a Microsoft 365 per tutti i domini sip utilizzati dagli endpoint. Non è possibile creare account di risorse online se i record DNS puntano a locali. Per ulteriori informazioni, vedere [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).

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
A questo punto è possibile rimuovere la distribuzione locale di [Skype for Business.](decommission-remove-on-prem.md)

## <a name="see-also"></a>Vedere anche

- [Rimuovi le autorizzazioni dell'ambiente locale Skype for Business](decommission-on-prem-overview.md)

- [Spostare tutti gli utenti necessari da locale a online](decommission-move-on-prem-users.md)

- [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md)

- [Rimuovere la distribuzione locale di Skype for Business](decommission-remove-on-prem.md)




