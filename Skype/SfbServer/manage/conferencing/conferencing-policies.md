---
title: Gestire i criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Riepilogo: informazioni su come gestire i criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: fc069093b9cc7cf5ce0e1e1f1efc0ee9e18e335d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818647"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Gestire i criteri di conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire i criteri di conferenza in Skype for Business Server.
  
Questo argomento descrive come gestire i criteri di conferenza. Per altre informazioni su come pianificare e distribuire i servizi di conferenza, vedere [pianificare le conferenze in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e [distribuire servizi di conferenza in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
I criteri di conferenza consentono di definire una vasta gamma di opzioni di pianificazione e partecipazione, che vanno dal fatto che una riunione possa includere l'audio e il video IP al numero massimo di persone che possono partecipare. È possibile usare i criteri di conferenza per gestire la sicurezza, la larghezza di banda e gli aspetti legali delle riunioni.
  
È possibile definire i criteri di conferenza su tre livelli: ambito globale, ambito del sito e ambito utente. Le impostazioni si applicano a un utente specifico dall'ambito più stretto all'ambito più ampio. Se si assegna un criterio a un utente, queste impostazioni hanno la precedenza. Se non si assegna un criterio utente, le impostazioni del sito si applicano. Se non si applicano criteri per l'utente o il sito, i criteri globali forniscono le impostazioni predefinite.
  
Un criterio globale esiste per impostazione predefinita, quindi non è possibile creare un nuovo criterio globale. Non è inoltre possibile eliminare i criteri globali esistenti, ma è possibile modificare i criteri globali esistenti per personalizzare le impostazioni predefinite.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Gestire i criteri di conferenza tramite il pannello di controllo di Skype for Business Server

Per gestire i criteri di conferenza tramite il pannello di controllo di Skype for Business Server:
  
1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri di conferenza**.
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Gestire i criteri di conferenza tramite Skype for Business Server Management Shell

Per gestire le riunioni tramite Skype for Business Server Management Shell, usare i cmdlet seguenti:
  
**Impostazioni dei criteri di conferenza**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Restituisce informazioni sui criteri di conferenza configurati per l'uso nell'organizzazione.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Assegna un criterio per i servizi di conferenza nell'ambito per utente.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crea un nuovo criterio di conferenza per l'uso nell'organizzazione.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Rimuove i criteri di conferenza specificati.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifica un criterio di conferenza esistente.  <br/> |
   

