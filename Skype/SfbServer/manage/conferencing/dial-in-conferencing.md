---
title: Gestire le conferenze telefoniche con accesso esterno in Skype for Business Server
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
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Riepilogo: informazioni su come gestire le conferenze telefoniche con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 6bf5f13075b54d904ae70bc1b2106253442135db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119485"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Gestire le conferenze telefoniche con accesso esterno in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire le conferenze telefoniche con accesso esterno in Skype for Business Server.
  
In questo argomento viene descritto come gestire le conferenze telefoniche con accesso esterno. Per ulteriori informazioni su come pianificare e configurare le conferenze telefoniche con accesso esterno durante la distribuzione, vedere [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) e Configure [dial-in conferencing in Skype for Business Server.](../../deploy/deploy-conferencing/dial-in-conferencing.md)
  
È possibile eseguire le attività seguenti per gestire le conferenze telefoniche con accesso esterno: abilitare o disabilitare le conferenze telefoniche con accesso esterno, gestire i numeri di accesso, gestire i criteri PIN per le conferenze telefoniche con accesso esterno, gestire l'accesso alla conferenza e lasciare annunci, modificare i mapping dei tasti per i comandi DTMF e accogliere gli utenti nelle conferenze telefoniche con accesso esterno. 
  
Per ulteriori informazioni sulla gestione dei dial plan, vedere [Creare o modificare un dial plan in Skype for Business Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)
  
Per ulteriori informazioni sull'utilizzo PSTN, vedere [Configure voice policies, PSTN usage records, and voice routes in Skype for Business.](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Gestire le conferenze telefoniche con accesso esterno tramite il Pannello di controllo di Skype for Business Server

Per gestire le informazioni sulle conferenze telefoniche con accesso esterno:
  
1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire il Pannello di controllo di Skype for Business Server.
    
3. Nella barra di spostamento sinistra fare clic su **Servizio di conferenza**.
    
Per gestire le informazioni sui dial plan e sull'utilizzo PSTN:
  
1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire il Pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **Routing vocale.**
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Gestire le conferenze telefoniche con accesso esterno tramite Skype for Business Server Management Shell

Per gestire le conferenze telefoniche con accesso esterno tramite Skype for Business Server Management Shell, utilizzare i cmdlet seguenti:
  
**Impostazioni di configurazione per l'accesso remoto**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Restituisce informazioni sulle directory conferenze configurate per l'utilizzo nell'organizzazione. Le directory conferenze vengono utilizzate per consentire agli utenti di conferenze telefoniche con accesso esterno di individuare le informazioni sulle conferenze.  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera informazioni sulla risposta di Skype for Business Server quando gli utenti aderiscono o abbandonano una conferenza telefonica con accesso remoto.  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Restituisce informazioni su tutti i numeri di accesso alle conferenze telefoniche con accesso esterno configurati per l'utilizzo nell'organizzazione.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Restituisce le impostazioni di segnalazione DTMF (Dual Tone Multi-Frequency) utilizzate per le conferenze telefoniche con accesso esterno. La tecnologia DTMF consente agli utenti che accedono dall'esterno a una conferenza di controllarne le impostazioni, ad esempio disattivare o riattivare il proprio audio oppure bloccare e sbloccare la conferenza, mediante la tastiera del telefono.  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Restituisce un elenco di lingue, incluse le lingue regionali/di minoranza, supportate per l'utilizzo con le conferenze telefoniche con accesso remoto di Skype for Business Server. Queste lingue vengono utilizzate per trasmettere messaggi e istruzioni audio agli utenti che partecipano a una conferenza tramite telefono.  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Restituisce informazioni sui dial plan utilizzati nell'organizzazione.  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Assegna un dial plan a uno o più utenti o gruppi.  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa le directory conferenze da Microsoft Office Communications Server 2007 R2 a Skype for Business Server. Ciò consente di garantire l'interoperabilità tra Skype for Business Server e Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Sposta una directory conferenze esistente da un pool all'altro.  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crea una nuova directory conferenze da utilizzare nell'organizzazione.  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crea un nuovo numero di accesso per le conferenze telefoniche con accesso esterno.  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione delle conferenze telefoniche con accesso esterno. Queste impostazioni determinano la risposta di Skype for Business Server quando gli utenti aderiscono o abbandonano una conferenza telefonica con accesso remoto. In particolare, vengono restituite informazioni sul fatto che i partecipanti siano tenuti o meno a registrare il proprio nome durante la partecipazione a una conferenza e su come (o se) il sistema annuncia che qualcuno si è unito o ha lasciato la chiamata.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Crea una nuova raccolta di impostazioni di segnalazione DTMF (Dual Tone Multi-Frequency) utilizzate per le conferenze telefoniche con accesso esterno.  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crea un nuovo dial plan.  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Rimuove una directory conferenze esistente.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Rimuove un numero di accesso esistente per le conferenze telefoniche con accesso esterno.  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Rimuove una o più raccolte di impostazioni di configurazione delle conferenze telefoniche con accesso esterno. Queste impostazioni determinano la risposta di Skype for Business Server quando gli utenti aderiscono o abbandonano una conferenza telefonica con accesso remoto.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Rimuove una raccolta esistente di impostazioni di segnalazione DTMF (Dual Tone Multi-Frequency) utilizzate per le conferenze telefoniche con accesso esterno.  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica i valori delle proprietà di un numero di accesso a conferenze telefoniche con accesso esterno esistente.  <br/> |
|[Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifica le impostazioni che determinano la risposta di Skype for Business Server quando gli utenti aderiscono o abbandonano una conferenza telefonica con accesso remoto.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica le impostazioni della segnalazione DTMF (Dual Tone Multi-Frequency) per le conferenze telefoniche con accesso esterno.  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica un dial plan esistente.  <br/> |
   
**Impostazioni dei criteri PIN**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Restituisce informazioni sui criteri PIN client configurati per l'utilizzo nell'organizzazione. L'autenticazione PIN consente agli utenti di accedere a Skype for Business Server fornendo un PIN anziché un nome utente e una password.  <br/> |
|[Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Assegna un criterio PIN client a un utente o a un gruppo di utenti.  <br/> |
|[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crea un nuovo criterio PIN (Personal Identification Number) del client.  <br/> |
|[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Rimuove il criterio PIN specificato.  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica uno o più criteri PIN client esistenti.  <br/> |
