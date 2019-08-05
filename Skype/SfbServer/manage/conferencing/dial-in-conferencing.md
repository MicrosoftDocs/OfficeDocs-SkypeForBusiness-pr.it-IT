---
title: Gestire i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Riepilogo: informazioni su come gestire i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: e27ee84769d2ba25b3d3ea6689c7125889b4f80e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189665"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Gestire i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.
  
Questo argomento descrive come gestire i servizi di conferenza telefonica con accesso esterno. Per altre informazioni su come pianificare e configurare le conferenze telefoniche con accesso esterno in fase di distribuzione, vedere [pianificare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) e configurare i servizi di [conferenza telefonica con accesso esterno in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Per gestire i servizi di conferenza telefonica con accesso esterno, è possibile eseguire le attività seguenti: abilitare o disabilitare i servizi di conferenza telefonica con chiamata in ingresso, gestire i numeri di Access, gestire i criteri PIN per i servizi di conferenza telefonica, gestire gli annunci di conferenza e uscire, modificare i mapping dei tasti per DTMF comandi e benvenuto agli utenti per i servizi di conferenza telefonica con accesso esterno. 
  
Per altre informazioni sulla gestione dei dial plan, vedere [creare o modificare un dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
Per altre informazioni sull'uso PSTN, vedere [configurare i criteri vocali, i record di utilizzo PSTN e le route vocali in Skype for business](../../deploy/deploy-enterprise-voice/voice-and-pstn.md).
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Gestire i servizi di conferenza telefonica con accesso esterno tramite il pannello di controllo di Skype for Business Server

Per gestire le informazioni sui servizi di conferenza telefonica con accesso esterno:
  
1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**.
    
Per gestire le informazioni sui dial plan e sull'utilizzo PSTN:
  
1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **routing vocale**.
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Gestire i servizi di conferenza telefonica con accesso esterno con Skype for Business Server Management Shell

Per gestire i servizi di conferenza telefonica con accesso esterno tramite Skype for Business Server Management Shell, usare i cmdlet seguenti:
  
**Impostazioni di configurazione con accesso esterno**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Restituisce informazioni sulle directory conferenza configurate per l'uso nell'organizzazione. Le directory conferenze vengono utilizzate per consentire agli utenti di conferenze telefoniche con accesso esterno di individuare le informazioni sulle conferenze.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera informazioni sul modo in cui Skype for Business Server risponde quando gli utenti partecipano o lasciano una conferenza telefonica con accesso esterno.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Restituisce informazioni su tutti i numeri di accesso per le conferenze telefoniche con chiamata in ingresso configurati per l'uso nell'organizzazione.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Restituisce le impostazioni di segnalazione DTMF (Dual Tone Multi-Frequency) usate per i servizi di conferenza telefonica con accesso esterno. DTMF consente agli utenti che effettuano la chiamata a una conferenza di controllare le impostazioni della conferenza, ad esempio per disattivare e riattivare l'audioconferenza o bloccare o sbloccare la conferenza, usando la tastiera del telefono.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Restituisce un elenco di lingue, incluse le lingue regionali/minoritarie, supportate per l'uso con le conferenze telefoniche con accesso esterno di Skype for Business Server. Queste lingue vengono usate per inoltrare i messaggi audio e le istruzioni agli utenti che partecipano a una conferenza usando un telefono.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Restituisce informazioni sui dial plan usati nell'organizzazione.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Assegna un dial plan a uno o più utenti o gruppi.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa le directory conferenza da Microsoft Office Communications Server 2007 R2 a Skype for Business Server. Ciò consente di garantire l'interoperabilità tra Skype for Business Server e Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Sposta una directory conferenze esistente da un pool all'altro.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crea una nuova directory conferenze da utilizzare nell'organizzazione.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crea un nuovo numero di accesso per i servizi di conferenza telefonica con chiamata in ingresso.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione per i servizi di conferenza telefonica con accesso esterno. Queste impostazioni determinano in che modo Skype for Business Server risponde quando gli utenti partecipano o lasciano una conferenza telefonica con accesso esterno. In particolare vengono restituite informazioni relative alla necessità o meno dei partecipanti di registrare il proprio nome quando partecipano a una conferenza e come (o se) il sistema annuncia che qualcuno ha aderito o lasciato la chiamata.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Crea una nuova raccolta di impostazioni di segnalazione DTMF (Dual-Tone Multi-Frequency) usate per i servizi di conferenza telefonica con accesso esterno.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crea un nuovo dial plan.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Rimuove una directory conferenze esistente.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Consente di rimuovere un numero di accesso esterno per i servizi di conferenza telefonica esistente.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Consente di rimuovere una o più raccolte di impostazioni di configurazione dei servizi di conferenza telefonica con accesso esterno. Queste impostazioni determinano in che modo Skype for Business Server risponde quando gli utenti partecipano o lasciano una conferenza telefonica con accesso esterno.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Rimuove una raccolta esistente di impostazioni di segnalazione DTMF (Dual-Tone Multi-Frequency) usate per i servizi di conferenza telefonica con accesso esterno.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica i valori delle proprietà di un numero di accesso esterno per i servizi di conferenza telefonica esistente.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifica le impostazioni che determinano il modo in cui Skype for Business Server risponde quando gli utenti partecipano o lasciano una conferenza telefonica con accesso esterno.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica le impostazioni di segnalazione DTMF (Dual Tone Multifrequency) usate per i servizi di conferenza telefonica con accesso esterno.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica un dial plan esistente.  <br/> |
   
**Impostazioni dei criteri PIN**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Restituisce informazioni sui criteri PIN (client Personal Identification Number) configurati per l'uso nell'organizzazione. L'autenticazione tramite PIN consente agli utenti di accedere a Skype for Business Server fornendo un PIN anziché un nome utente e una password.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Assegna un criterio PIN (client Personal Identification Number) a un utente o un gruppo di utenti.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crea un nuovo criterio PIN (client Personal Identification Number).  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Rimuove il criterio PIN (Personal Identification Number) specificato.  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica uno o più criteri PIN (client Personal Identification Number) esistenti.  <br/> |
   

