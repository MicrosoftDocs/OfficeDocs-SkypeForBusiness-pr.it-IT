---
title: Installare e configurare le opzioni di occupato per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Informazioni su come installare e configurare le opzioni di occupato in Skype for Business Server.
ms.openlocfilehash: e1480809eb1f14dd25837d11fd54ed6bb5cac534
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830806"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Installare e configurare le opzioni di occupato per Skype for Business Server

Informazioni su come installare e configurare le opzioni di occupato in Skype for Business Server.

Busy options è un nuovo criterio vocale introdotto nell'aggiornamento cumulativo di luglio 2016 che consente di configurare il modo in cui le chiamate in arrivo vengono gestite quando un utente è già in una chiamata o in una conferenza o ha una chiamata in attesa. Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica.

Se per l'organizzazione sono abilitate le opzioni di disponibilità, tutti gli utenti dell'azienda, sia VoIP aziendale che utenti non di VoIP aziendale, possono utilizzare le opzioni di configurazione seguenti:

- Occupato su occupato-in cui le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato se l'utente è occupato.

- Segreteria telefonica su occupato-in cui le nuove chiamate in entrata verranno inoltrate alla segreteria telefonica se l'utente è occupato.

Indipendentemente dal modo in cui sono configurate le opzioni di disponibilità, gli utenti di una chiamata o di una conferenza o di quelli con una chiamata in attesa non sono stati impediti dall'avvio di nuove chiamate o conferenze.

Per ulteriori informazioni sulla funzionalità di opzioni di occupato, vedere [Plan for Busy options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Installare

Assicurarsi di avere installato la versione più recente di Skype for Business Server e di aver installato la patch più recente. A tale scopo, arrestare innanzitutto tutti i servizi, quindi eseguire il programma di installazione dell'aggiornamento di Skype for Business Server come indicato di seguito:

1. Eseguire il comando Stop-CsWindowsService.

2. Eseguire il programma di installazione di SkypeServerUpdateInstaller.exe su ogni Front End Server in un pool.

3. Eseguire il programma di installazione di SkypeServerUpdateInstaller.exe su ogni Survivable Branch Server (SBS), se si desidera garantire il supporto per il failover su SBS.

Il programma di installazione distribuirà la versione più recente dell'applicazione per le opzioni di occupato. Tuttavia, l'applicazione non è abilitata per impostazione predefinita. Per abilitare l'applicazione, eseguire le operazioni seguenti:

1. Eseguire il cmdlet [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) per abilitare globalmente le opzioni di occupato, come illustrato nell'esempio seguente:

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Successivamente, se il sito dispone di un criterio vocale, è necessario abilitare le opzioni di disponibilità per il criterio vocale, come indicato di seguito:

    Prima di tutto, eseguire [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) per recuperare il nome del sito:

   ```powershell
   Get-CsSite
   ```

    Utilizzare il valore Identity, ad esempio site: Redmond1, Estratto da Get-CsSite per recuperare il criterio vocale del sito come indicato di seguito:

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Se esiste un criterio vocale per il sito, eseguire il comando riportato di seguito:

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Successivamente, eseguire il cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) per aggiungere le opzioni di occupato all'elenco delle applicazioni server, come illustrato nell'esempio seguente:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > È necessario sostituire% FQDN% con il nome di dominio completo di un pool specifico.

4. Successivamente, eseguire il cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) per aggiornare i ruoli di controllo di accesso basato sui ruoli (RBAC) per i cmdlet delle opzioni di occupato, come illustrato nell'esempio seguente:

   ```powershell
   Update-CsAdminRole
   ```

5. Infine, avviare Skype for Business Server Windows Services in tutti i front end server in tutti i pool in cui sono state installate e abilitate le opzioni di occupato eseguendo il comando [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configurazione

Per configurare le opzioni di occupato, utilizzare il cmdlet [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .

Ad esempio, il comando seguente consente di configurare le opzioni di disponibilità per l'utente "Ken". In questa configurazione, qualsiasi chiamata a "Ken ' s" restituirà un segnale di occupato quando è già in una chiamata:

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

Nell'esempio riportato di seguito, il comando Configura le opzioni di disponibilità per l'utente "Chrystal Velasquez". In questa configurazione, le nuove chiamate in entrata su "Chrystal Velasquez" verranno inoltrate alla segreteria telefonica quando è già in corso una chiamata:

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

È possibile recuperare le informazioni di configurazione relative alle opzioni di occupato utilizzando il cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) . Nell'esempio seguente viene restituita l'impostazione delle opzioni di occupato per "KenMyer@Contoso.com":

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

È possibile rimuovere le opzioni di occupato utilizzando il cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) . Con il comando seguente vengono rimosse le opzioni di disponibilità per "Ken":

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Per informazioni dettagliate sui cmdlet che è possibile utilizzare per configurare le opzioni di occupato, vedere il contenuto di riferimento tecnico per [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)e [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Abilitare la registrazione

Per abilitare la registrazione per le opzioni di occupato tramite il servizio di registrazione centralizzato, specificare quanto segue:

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Verifica e risoluzione dei problemi

Dopo aver installato le opzioni di occupato, è possibile verificare che l'installazione abbia avuto esito positivo utilizzando il cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) per recuperare l'elenco delle applicazioni server. Se le opzioni di occupato sono installate correttamente, l'output del cmdlet dovrebbe mostrare la configurazione delle opzioni di occupato come indicato di seguito:

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

È inoltre possibile utilizzare il Visualizzatore eventi di Windows per verificare che l'installazione delle opzioni occupate abbia avuto esito positivo e che Skype for Business Server abbia caricato correttamente le opzioni di occupato. Per verificare le opzioni di occupato, aprire il **Visualizzatore eventi- \> registri applicazioni e servizi- \> Server Skype (o Lync)** e cercare l'ID evento = 30253.
