---
title: Distribuire l'aspetto della linea condivisa in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Leggere questo argomento per informazioni su come distribuire l'aspetto di linea condiviso (SLA, Shared Line Appearance) in Skype for Business Server 2015, novembre 2015 Cumulative Update. SLA è una funzionalità per la gestione di più chiamate su un numero specifico denominato numero condiviso.
ms.openlocfilehash: a692768744782f547b57b635a58864c858389d7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812406"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Distribuire l'aspetto della linea condivisa in Skype for Business Server 2015

Leggere questo argomento per informazioni su come distribuire l'aspetto di linea condiviso (SLA, Shared Line Appearance) in Skype for Business Server 2015, novembre 2015 Cumulative Update. SLA è una funzionalità per la gestione di più chiamate su un numero specifico denominato numero condiviso.

Per ulteriori informazioni su questa funzionalità, vedere [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

SLA (Shared Line Appearance) è una nuova funzionalità di Skype for Business Server, aggiornamento cumulativo di novembre 2015. Per abilitare questa funzionalità, è necessario che sia stata distribuita per la prima volta questo aggiornamento cumulativo.

### <a name="install-shared-line-appearance"></a>Installare l'aspetto della linea condivisa

1. Dopo aver distribuito l'aggiornamento cumulativo di Skype for Business Server, novembre 2015, eseguire la  `SkypeServerUpdateInstaller.exe` patch su ogni Front End Server nel pool.

2. Il programma di installazione distribuirà la versione più recente dell'applicazione SLA, tuttavia, l'applicazione non è abilitata per impostazione predefinita. Questa impostazione è abilitata attenendosi alla procedura descritta di seguito:

    a. Registrare SLA come applicazione server eseguendo il comando seguente per ogni pool:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   dove% FQDN% è il nome di dominio completo del pool.

    b. Eseguire il seguente comando per aggiornare i ruoli RBAC per i cmdlet di SLA:

   ```powershell
   Update-CsAdminRole
   ```

    c. Riavviare tutti i Front End Server (servizio RTCSRV) in tutti i pool in cui è stato installato e abilitato SLA:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Creare un gruppo di SLA e aggiungervi gli utenti

1. Creare il gruppo di SLA utilizzando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Il cmdlet Set-CsSlaConfiguration contrassegna l'account VoIP aziendale SLAGroup1 come entità SLA e il numero di SLAGroup1 diventa il numero del gruppo di SLA. Tutte le chiamate a SLAGroup1 suoneranno l'intero gruppo del contratto di servizio.

    Nell'esempio seguente viene creato un gruppo di SLA per un utente VoIP aziendale esistente, SLAGroup1, e viene utilizzato il numero assegnato a SLAGroup1 come numero della linea principale del contratto di servizio.

    Il comando imposta il numero massimo di chiamate simultanee per il nuovo gruppo di SLA su 3 e per le chiamate superiori a quelle per ascoltare un segnale di occupato:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    È possibile utilizzare Set-CsSlaConfiguration per creare un nuovo gruppo di SLA o modificarne uno esistente.

    > [!NOTE]
    > Si noti che il valore specificato per  `-Identity` deve essere un account utente esistente abilitato per VoIP aziendale valido.

2. Aggiungere delegati al gruppo utilizzando il cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) :

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    Nell'esempio seguente viene aggiunto un utente al gruppo di SLA. Ogni utente aggiunto al gruppo deve essere un utente abilitato VoIP aziendale valido:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Ripetere il cmdlet per ogni utente che si desidera aggiungere al gruppo. Gli utenti possono appartenere solo a un singolo gruppo di SLA.

### <a name="configure-the-sla-group-busy-option"></a>Configurare l'opzione occupato del gruppo di SLA

- Configurare l'opzione occupato del gruppo di SLA utilizzando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    Nell'esempio seguente vengono impostate le chiamate che superano il numero massimo di chiamate simultanee da inoltrare al numero di telefono 202-555-1234. La destinazione potrebbe essere un utente dell'organizzazione invece di un numero di telefono; in tal caso, la sintassi per la persona che riceve le chiamate inoltrate è la stessa di quando si specifica un delegato:  `sip:<NameofDelegate@domain>` . L'altro parametro possibile per  `BusyOption` è `Voicemail` :

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Configurare l'opzione di chiamata senza risposta del gruppo di SLA

1. Configurare l'opzione di chiamata senza risposta del gruppo SLA utilizzando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. Nell'esempio seguente viene specificato che le chiamate perse devono essere inoltrate all'utente denominato  `sla_forward_number` . Le opzioni valide per il  `-MissedCallOption` parametro sono `Forward` ,  `BusySignal` o  `Disconnect` . Se si sceglie  `Forward` , è necessario includere anche il  `-MissedCallForwardTarget` parametro, con un utente o un numero di telefono come destinazione:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Rimuovere un delegato da un gruppo

- Rimuovere un delegato da un gruppo utilizzando il cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Ad esempio:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Eliminare un gruppo di SLA

- Eliminare un gruppo di SLA utilizzando il cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Ad esempio:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


