---
title: Distribuire l'aspetto della linea condivisa in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Leggere questo argomento per informazioni su come distribuire l'aspetto della linea condivisa (SLA) in Skype for Business Server 2015, aggiornamento cumulativo di novembre 2015. SLA è una funzionalità per la gestione di più chiamate su un numero specifico denominato numero condiviso.
ms.openlocfilehash: 040801c08490edb103fa195098ef8aa3483fc2e0
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924857"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Distribuire l'aspetto della linea condivisa in Skype for Business Server 2015

Leggere questo argomento per informazioni su come distribuire l'aspetto della linea condivisa (SLA) in Skype for Business Server 2015, aggiornamento cumulativo di novembre 2015. SLA è una funzionalità per la gestione di più chiamate su un numero specifico denominato numero condiviso.

Per altre informazioni su questa funzionalità, vedere [pianificare l'aspetto delle linee condivise in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

L'aspetto della linea condivisa (SLA) è una nuova funzionalità di Skype for Business Server, aggiornamento cumulativo di novembre 2015. Per abilitare questa funzionalità, è necessario aver prima distribuito questo aggiornamento cumulativo.

### <a name="install-shared-line-appearance"></a>Installare l'aspetto della linea condivisa

1. Dopo la distribuzione di Skype for Business Server, aggiornamento cumulativo di novembre 2015, `SkypeServerUpdateInstaller.exe` eseguire la patch su ogni server front-end nel pool.

2. Il programma di installazione distribuirà l'ultima versione dell'applicazione SLA, ma l'applicazione non è abilitata per impostazione predefinita. È abilitato seguendo i passaggi descritti di seguito:

    un. Registrare SLA come applicazione server eseguendo il comando seguente per ogni pool:

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   dove% FQDN% è il nome di dominio completo del pool.

    b. Eseguire il comando seguente per aggiornare i ruoli RBAC per i cmdlet SLA:

   ```
   Update-CsAdminRole
   ```

    c. Riavviare tutti i server front-end (servizio RTCSRV) in tutti i pool in cui è stato installato e abilitato SLA:

   ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Creare un gruppo di SLA e aggiungervi utenti

1. Creare il gruppo SLA usando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Il cmdlet Set-CsSlaConfiguration contrassegna l'account di VoIP aziendale SLAGroup1 come entità SLA e il numero di SLAGroup1 diventa il numero per il gruppo SLA. Tutte le chiamate a SLAGroup1 suoneranno l'intero gruppo SLA.

    L'esempio seguente crea un gruppo di SLA per un utente di VoIP aziendale esistente, SLAGroup1, e usa il numero assegnato a SLAGroup1 come numero principale di SLA.

    Il comando imposta il numero massimo di chiamate simultanee per il nuovo gruppo SLA su 3 e per le chiamate superiori a quelle per ascoltare un segnale di occupato:

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Puoi usare set-CsSlaConfiguration per creare un nuovo gruppo di SLA o modificarne uno esistente.

    > [!NOTE]
    > Tieni presente che ciò che specifichi `-Identity` per deve essere un account utente esistente abilitato per la voce Enterprise valido.

2. Aggiungere delegati al gruppo usando il cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) :

   ```
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    L'esempio seguente aggiunge un utente al gruppo SLA. Ogni utente aggiunto al gruppo deve essere un utente abilitato per la funzionalità VoIP aziendale valido:

   ```
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Ripetere il cmdlet per ogni utente che si vuole aggiungere al gruppo. Gli utenti possono appartenere solo a un singolo gruppo di SLA.

### <a name="configure-the-sla-group-busy-option"></a>Configurare l'opzione occupato gruppo SLA

- Configurare l'opzione occupato gruppo SLA usando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    L'esempio seguente imposta le chiamate che superano il numero massimo di chiamate simultanee da inoltrare al numero di telefono 202-555-1234. La destinazione può essere un utente dell'organizzazione invece di un numero di telefono; in questo caso, la sintassi per la persona che riceve le chiamate inoltrate è la stessa di quando si specifica un delegato: `sip:<NameofDelegate@domain>`. L'altro parametro possibile per `BusyOption` è `Voicemail`:

  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Configurare l'opzione di chiamata senza risposta del gruppo SLA

1. Configurare l'opzione di chiamata senza risposta del gruppo SLA usando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. L'esempio seguente specifica che le chiamate perse devono essere inoltrate all'utente denominato `sla_forward_number`. Le opzioni valide per il `-MissedCallOption` parametro sono `Forward` `BusySignal`, o `Disconnect`. Se si sceglie `Forward`, è necessario includere anche il `-MissedCallForwardTarget` parametro, con un utente o un numero di telefono come destinazione:

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Rimuovere un delegato da un gruppo

- Rimuovere un delegato da un gruppo usando il cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :

  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Ad esempio:

  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Eliminare un gruppo di SLA

- Eliminare un gruppo di SLA usando il cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :

  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Ad esempio:

  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


