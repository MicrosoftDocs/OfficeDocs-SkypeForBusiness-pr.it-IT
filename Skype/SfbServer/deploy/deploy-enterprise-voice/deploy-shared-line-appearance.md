---
title: Distribuire l'aspetto delle righe condivise in Skype for Business Server 2015
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
description: Leggere questo argomento per informazioni su come distribuire l'aspetto della linea condivisa in Skype for Business Server 2015, aggiornamento cumulativo di novembre 2015. Sla è una funzionalità per la gestione di più chiamate su un numero specifico denominato numero condiviso.
ms.openlocfilehash: de0b0d54fed0b76c1e20b67b743dfef2c4f784589b2eb3867529201493242e32
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314912"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Distribuire l'aspetto delle righe condivise in Skype for Business Server 2015

Leggere questo argomento per informazioni su come distribuire l'aspetto della linea condivisa in Skype for Business Server 2015, aggiornamento cumulativo di novembre 2015. Sla è una funzionalità per la gestione di più chiamate su un numero specifico denominato numero condiviso.

Per ulteriori informazioni su questa funzionalità, vedere [Plan for Shared Line Appearance in Skype for Business Server 2015.](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)

Shared Line Appearance (SLA) è una nuova funzionalità Skype for Business Server, aggiornamento cumulativo di novembre 2015. Per abilitare questa funzionalità, è necessario aver prima distribuito questo aggiornamento cumulativo.

### <a name="install-shared-line-appearance"></a>Installare l'aspetto linea condivisa

1. Dopo Skype for Business Server, viene distribuito l'aggiornamento cumulativo di novembre 2015, eseguire la patch in ogni `SkypeServerUpdateInstaller.exe` Front End Server del pool.

2. Il programma di installazione distribuirà la versione più recente dell'applicazione sla, tuttavia, l'applicazione non è abilitata per impostazione predefinita. È abilitato seguendo la procedura descritta di seguito:

    a. Registrare il contratto di servizio come applicazione server eseguendo il comando seguente per ogni pool:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   dove %FQDN% è il nome di dominio completo del pool.

    b. Eseguire il comando seguente per aggiornare i ruoli RBAC per i cmdlet sla:

   ```powershell
   Update-CsAdminRole
   ```

    c. Riavviare tutti i Front End Server (servizio RTCSRV) in tutti i pool in cui è stato installato e abilitato sla:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Creare un gruppo di contratti di servizio e aggiungerne utenti

1. Creare il gruppo sla utilizzando il cmdlet [Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Il cmdlet Set-CsSlaConfiguration contrassegna l'account VoIP aziendale SLAGroup1 come entità sla e il numero di SLAGroup1 diventa il numero per il gruppo sla. Tutte le chiamate a SLAGroup1 chiameranno l'intero gruppo sla.

    Nell'esempio seguente viene creato un gruppo di contratti di servizio per un utente di VoIP aziendale esistente, SLAGroup1, e viene utilizzato il numero assegnato a SLAGroup1 come numero della riga principale del contratto di servizio.

    Il comando imposta il numero massimo di chiamate simultanee per il nuovo gruppo di contratti di servizio su 3 e per le chiamate in eccesso per ascoltare un segnale di occupato:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    È possibile utilizzare Set-CsSlaConfiguration per creare un nuovo gruppo di contratti di servizio o modificarne uno esistente.

    > [!NOTE]
    > Si noti che ciò per cui si specifica deve essere un `-Identity` account utente VoIP aziendale esistente.

2. Aggiungere delegati al gruppo utilizzando il cmdlet [Add-CsSlaDelegates:](/powershell/module/skype/add-cssladelegates?view=skype-ps)

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    Nell'esempio seguente viene aggiunto un utente al gruppo sla. Ogni utente aggiunto al gruppo deve essere un VoIP aziendale valido:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Ripetere il cmdlet per ogni utente che si desidera aggiungere al gruppo. Gli utenti possono appartenere solo a un singolo gruppo di contratti di servizio.

### <a name="configure-the-sla-group-busy-option"></a>Configurare l'opzione disponibilità del gruppo sla

- Configurare l'opzione disponibilità del gruppo sla utilizzando il cmdlet [Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    Nell'esempio seguente vengono impostate chiamate che superano il numero massimo di chiamate simultanee da inoltrare al numero di telefono 202-555-1234. La destinazione potrebbe essere un utente dell'organizzazione anziché un numero di telefono. in tal caso, la sintassi per la persona che riceve le chiamate inoltrate è la stessa di quando si specifica un delegato:  `sip:<NameofDelegate@domain>` . L'altro parametro possibile  `BusyOption` per è `Voicemail` :

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Configurare l'opzione di chiamata senza chiamata senza contratto di servizio

1. Configurare l'opzione di chiamata senza chiamata senza contratto di servizio utilizzando il cmdlet [Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. Nell'esempio seguente viene specificato che le chiamate senza risposta devono essere inoltrate all'utente denominato  `sla_forward_number` . Le opzioni valide per il  `-MissedCallOption` parametro sono , o `Forward`  `BusySignal`  `Disconnect` . Se si sceglie , è necessario includere anche il parametro , con un utente o un numero  `Forward`  `-MissedCallForwardTarget` di telefono come destinazione:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Rimuovere un delegato da un gruppo

- Rimuovere un delegato da un gruppo utilizzando il cmdlet [Remove-CsSlaDelegates:](/powershell/module/skype/remove-cssladelegates?view=skype-ps)

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Ad esempio:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Eliminare un gruppo di contratti di servizio

- Eliminare un gruppo di contratti di servizio utilizzando il cmdlet [Remove-CsSlaConfiguration:](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Ad esempio:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```