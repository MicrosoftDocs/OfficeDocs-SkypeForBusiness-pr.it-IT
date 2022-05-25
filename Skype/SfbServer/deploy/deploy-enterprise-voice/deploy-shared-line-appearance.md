---
title: Distribuire l'aspetto della linea condivisa in Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Leggere questo argomento per informazioni su come distribuire l'aspetto della riga condivisa in Skype for Business Server aggiornamento cumulativo di novembre 2015. Il contratto di servizio è una funzionalità per la gestione di più chiamate su un numero specifico denominato numero condiviso.
ms.openlocfilehash: 7f9d904de2b3348bdf8ed75b9f0df38aee252cdd
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671592"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Distribuire l'aspetto della linea condivisa in Skype for Business Server 2015

Leggere questo argomento per informazioni su come distribuire l'aspetto della riga condivisa in Skype for Business Server aggiornamento cumulativo di novembre 2015. Il contratto di servizio è una funzionalità per la gestione di più chiamate su un numero specifico denominato numero condiviso.

Per altre informazioni su questa funzionalità, vedere [Plan for Shared Line Appearance in Skype for Business Server 2015.For more information about this feature, see Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Shared Line Appearance (SLA) è una nuova funzionalità dell'aggiornamento cumulativo di Skype for Business Server novembre 2015. Per abilitare questa funzionalità, è necessario aver prima distribuito questo aggiornamento cumulativo.

## <a name="install-shared-line-appearance"></a>Installare l'aspetto della linea condivisa

1. Dopo la distribuzione dell'aggiornamento cumulativo di novembre 2015 Skype for Business Server, eseguire la `SkypeServerUpdateInstaller.exe` patch in ogni Front End Server nel pool.

2. Il programma di installazione distribuirà la versione più recente dell'applicazione sla, tuttavia, l'applicazione non è abilitata per impostazione predefinita. È abilitata seguendo i passaggi descritti di seguito:

    a. Registrare il contratto di servizio come applicazione server eseguendo il comando seguente per ogni pool:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   dove %FQDN% è il nome di dominio completo del pool.

    b. Eseguire il comando seguente per aggiornare i ruoli del controllo degli accessi in base al ruolo per i cmdlet del contratto di servizio:

   ```powershell
   Update-CsAdminRole
   ```

    c. Riavviare tutti i front-end server (servizio RTCSRV) in tutti i pool in cui è stato installato e abilitato il contratto di servizio:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

## <a name="create-an-sla-group-and-add-users-to-it"></a>Creare un gruppo di contratti di servizio e aggiungervi utenti

1. Creare il gruppo di contratti di servizio usando il cmdlet [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Il cmdlet Set-CsSlaConfiguration contrassegna l'account VoIP aziendale SLAGroup1 come entità sla e il numero di SLAGroup1 diventa il numero per il gruppo di contratti di servizio. Tutte le chiamate a SLAGroup1 squilleranno all'intero gruppo di contratti di servizio.

    L'esempio seguente crea un gruppo di contratti di servizio per un utente VoIP aziendale esistente, SLAGroup1, e usa il numero assegnato per SLAGroup1 come numero di riga principale del contratto di servizio.

    Il comando imposta il numero massimo di chiamate simultanee per il nuovo gruppo di contratti di servizio su 3 e per le chiamate in eccesso per ascoltare un segnale occupato:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    È possibile usare Set-CsSlaConfiguration per creare un nuovo gruppo di contratti di servizio o modificarne uno esistente.

    > [!NOTE]
    > Si noti che l'oggetto specificato per deve essere un account utente esistente valido abilitato per `-Identity` VoIP aziendale.

2. Aggiungere delegati al gruppo usando il cmdlet [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates) :

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
   ```

    Nell'esempio seguente viene aggiunto un utente al gruppo di contratti di servizio. Ogni utente aggiunto al gruppo deve essere un utente valido abilitato VoIP aziendale:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Ripetere il cmdlet per ogni utente da aggiungere al gruppo. Gli utenti possono appartenere solo a un singolo gruppo di contratti di servizio.

## <a name="configure-the-sla-group-busy-option"></a>Configurare l'opzione Occupato gruppo di contratti di servizio

- Configurare l'opzione Occupato del gruppo di contratti di servizio usando il cmdlet [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) :

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    Nell'esempio seguente vengono impostate chiamate che superano il numero massimo di chiamate simultanee da inoltrare al numero di telefono 202-555-1234. La destinazione potrebbe essere un utente dell'organizzazione anziché un numero di telefono; in tal caso, la sintassi per la ricezione delle chiamate inoltrate è la stessa di quando si specifica un delegato:  `sip:<NameofDelegate@domain>`. L'altro parametro possibile per  `BusyOption` è `Voicemail`:

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

## <a name="configure-the-sla-group-missed-call-option"></a>Configurare l'opzione chiamata senza risposta del gruppo di contratti di servizio

1. Configurare l'opzione Chiamata senza risposta del gruppo di contratti di servizio usando il cmdlet [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. Nell'esempio seguente viene specificato che le chiamate perse devono essere inoltrate all'utente denominato  `sla_forward_number`. Le opzioni valide per il  `-MissedCallOption` parametro sono `Forward`,  `BusySignal`o  `Disconnect`. Se si sceglie  `Forward`, è necessario includere anche il  `-MissedCallForwardTarget` parametro , con un utente o un numero di telefono come destinazione:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

## <a name="remove-a-delegate-from-a-group"></a>Rimuovere un delegato da un gruppo

- Rimuovere un delegato da un gruppo usando il cmdlet [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates) :

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Ad esempio:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

## <a name="delete-an-sla-group"></a>Eliminare un gruppo di contratti di servizio

- Eliminare un gruppo di contratti di servizio usando il cmdlet [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration) :

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Ad esempio:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```
