---
title: Gestire le impostazioni di configurazione delle riunioni in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Riepilogo: informazioni su come gestire le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: d9ed049fe4873428729149e1ea624bf715bb81ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189650"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Gestire le impostazioni di configurazione delle riunioni in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire le impostazioni di configurazione delle riunioni in Skype for Business Server.
  
Questo argomento descrive come gestire le impostazioni di configurazione delle riunioni. Per altre informazioni su come pianificare e distribuire i servizi di conferenza, vedere [pianificare le conferenze in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e [distribuire servizi di conferenza in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Le impostazioni di configurazione della riunione dettano il tipo di riunioni che gli utenti possono creare, oltre a controllare come (o anche se) utenti anonimi e servizi di conferenza telefonica con accesso esterno possono partecipare a queste riunioni. Tieni presente che queste impostazioni influenzano solo le riunioni programmate; non influiscono sulle riunioni ad hoc create facendo clic sull'opzione incontra ora in Skype for business.
  
Le impostazioni di configurazione della riunione definiscono le seguenti:
  
- Se gli utenti che effettuano la chiamata dalla rete PSTN (Public Switched Telephone Network) accedono alla sala di attesa
    
- Chi può essere un relatore
    
- Se il tipo di conferenza è assegnato per impostazione predefinita
    
- Se gli utenti anonimi (non autenticati) sono ammessi per impostazione predefinita
    
Puoi definire le caratteristiche delle riunioni usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell. 
  
Puoi specificare le impostazioni delle riunioni a livello globale (creato per impostazione predefinita), livello di sito o livello di pool. Per impostazione predefinita, le impostazioni globali definiscono l'esperienza della riunione. Se crei impostazioni a livello di pool, queste impostazioni si applicano a tutte le riunioni ospitate da tale pool. Se non si creano impostazioni a livello di pool, le impostazioni a livello di sito si applicano, se esistenti. Se non si definiscono le impostazioni a livello di sito, le impostazioni globali si applicano a tutte le riunioni.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Gestire le impostazioni delle riunioni tramite il pannello di controllo di Skype for Business Server

Per gestire le impostazioni delle riunioni tramite il pannello di controllo di Skype for Business Server:
  
1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **Configurazione riunione**.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Gestire le impostazioni delle riunioni tramite Skype for Business Server Management Shell

Per gestire le riunioni tramite Skype for Business Server Management Shell, usare i cmdlet seguenti:
  
**Impostazioni di configurazione delle riunioni**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Restituisce informazioni sulle impostazioni di configurazione della riunione attualmente in uso nell'organizzazione.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione della riunione nell'ambito del sito o del servizio.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Elimina una raccolta esistente di impostazioni di configurazione della riunione.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica le impostazioni di configurazione della riunione attualmente in uso nell'organizzazione.  <br/> |
   

