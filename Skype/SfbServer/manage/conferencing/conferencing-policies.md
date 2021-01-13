---
title: Gestire i criteri di conferenza in Skype for Business Server
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
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Riepilogo: informazioni su come gestire i criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: 3ad59f186ccc4bebdefae1a6bfefdf04e9bf6851
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835276"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Gestire i criteri di conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire i criteri di conferenza in Skype for Business Server.
  
In questo argomento viene descritto come gestire i criteri di conferenza. Per ulteriori informazioni su come pianificare e distribuire le conferenze, vedere [Plan for Conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e [deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
I criteri di conferenza consentono di definire una vasta gamma di opzioni di pianificazione e partecipazione, che variano dal fatto che una riunione possa includere audio e video IP per il numero massimo di utenti che possono partecipare. È possibile utilizzare i criteri di conferenza per gestire la sicurezza, la larghezza di banda e gli aspetti legali delle riunioni.
  
È possibile definire un criterio di conferenza su tre livelli: ambito globale, ambito sito e ambito utente. Le impostazioni si applicano a un utente specifico partendo dall'ambito più ristretto fino all'ambito più ampio. Se si assegna un criterio a un utente, tali impostazioni avranno la precedenza. Se non si assegna un criterio utente, si applicano le impostazioni sito. Se non si applica alcun criterio utente o sito, le impostazioni predefinite vengono fornite dal criterio globale.
  
Poiché esiste un criterio globale per impostazione predefinita, non è possibile crearne uno nuovo. Non è possibile inoltre eliminare il criterio globale esistente, ma è possibile modificarlo per personalizzare le impostazioni predefinite.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Gestire i criteri di conferenza tramite il pannello di controllo di Skype for Business Server

Per gestire i criteri di conferenza tramite il pannello di controllo di Skype for Business Server:
  
1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza** e quindi su **criteri conferenza**.
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Gestire i criteri di conferenza tramite Skype for Business Server Management Shell

Per gestire le riunioni tramite Skype for Business Server Management Shell, utilizzare i cmdlet seguenti:
  
**Impostazioni per i criteri di conferenza**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Restituisce informazioni sui criteri conferenza configurati per l'utilizzo nell'organizzazione.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Assegna un criterio di conferenza nell'ambito per utente.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crea un nuovo criterio relativo alle conferenze da utilizzare all'interno dell'organizzazione.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Rimuove il criterio conferenza specificato.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Consente di modificare un criterio di conferenza.  <br/> |
   

