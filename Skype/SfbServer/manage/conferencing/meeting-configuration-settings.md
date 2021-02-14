---
title: Gestire le impostazioni di configurazione delle riunioni in Skype for Business Server
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Riepilogo: informazioni su come gestire le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: c34723219839061e36b2684dff81efd5cd914843
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828086"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Gestire le impostazioni di configurazione delle riunioni in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire le impostazioni di configurazione delle riunioni in Skype for Business Server.
  
In questo argomento viene descritto come gestire le impostazioni di configurazione delle riunioni. Per ulteriori informazioni su come pianificare e distribuire le conferenze, vedere Pianificare le conferenze [in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e Distribuire le conferenze in Skype for Business [Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
Le impostazioni di configurazione delle riunioni determinano il tipo di riunioni che gli utenti possono creare, oltre a controllare come (o anche se) gli utenti anonimi e gli utenti di conferenze telefoniche con accesso esterno possono partecipare a queste riunioni. Si noti che queste impostazioni influiscono solo sulle riunioni pianificate; non influiscono sulle riunioni ad hoc create facendo clic sull'opzione Riunione ora in Skype for Business.
  
Le impostazioni di configurazione delle riunioni definiscono quanto segue:
  
- Se gli utenti con accesso esterno dalla rete PSTN (Public Switched Telephone Network) devono transitare per la sala di attesa
    
- Chi può svolgere il ruolo di relatore
    
- Se il tipo di conferenza viene assegnato per impostazione predefinita
    
- Se gli utenti anonimi (non autenticati) sono ammessi per impostazione predefinita
    
È possibile definire le caratteristiche delle riunioni utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell. 
  
È possibile specificare le impostazioni delle riunioni a livello globale (creato per impostazione predefinita), a livello di sito o di pool. Per impostazione predefinita, le impostazioni globali definiscono l'esperienza di riunione. Se si creano impostazioni a livello di pool, tali impostazioni si applicheranno a tutte le riunioni ospitate da tale pool. Se invece non si creano impostazioni a livello di pool, si applicheranno le impostazioni a livello di sito, se esistenti. Se non si definiscono impostazioni a livello di sito, le impostazioni globali si applicheranno a tutte le riunioni.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Gestire le impostazioni delle riunioni tramite il Pannello di controllo di Skype for Business Server

Per gestire le impostazioni delle riunioni tramite il Pannello di controllo di Skype for Business Server:
  
1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire il Pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su Servizio **di** conferenza e quindi su **Configurazione riunione.**
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Gestire le impostazioni delle riunioni tramite Skype for Business Server Management Shell

Per gestire le riunioni tramite Skype for Business Server Management Shell, utilizzare i cmdlet seguenti:
  
**Impostazioni di configurazione delle riunioni**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Restituisce informazioni sulle impostazioni di configurazione delle riunioni attualmente in uso nell'organizzazione.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione delle riunioni nell'ambito del sito o del servizio.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Elimina una raccolta esistente di impostazioni di configurazione delle riunioni.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica le impostazioni di configurazione delle riunioni attualmente in uso nell'organizzazione.  <br/> |
   

