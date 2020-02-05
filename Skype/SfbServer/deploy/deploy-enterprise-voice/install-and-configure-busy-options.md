---
title: Installare e configurare le opzioni di occupato per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Leggere informazioni su come installare e configurare le opzioni di occupato in Skype for Business Server.
ms.openlocfilehash: dd22d07bcabc86b0d16f3ad1029087b659a3e4a5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767219"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Installare e configurare le opzioni di occupato per Skype for Business Server

Leggere informazioni su come installare e configurare le opzioni di occupato in Skype for Business Server.

Opzioni di occupato è un nuovo criterio vocale introdotto nell'aggiornamento cumulativo di 2016 di luglio che consente di configurare il modo in cui vengono gestite le chiamate in arrivo quando un utente è già in una chiamata o una conferenza o se è stata inserita una chiamata in attesa. Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica.

Se le opzioni di occupato sono abilitate per l'organizzazione, tutti gli utenti dell'azienda, sia VoIP aziendale che utenti non aziendali, possono usare le opzioni di configurazione seguenti:

- Occupato in busy-in cui le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato se l'utente è occupato.

- Segreteria telefonica in occupato, in cui le nuove chiamate in arrivo verranno inoltrate alla segreteria telefonica se l'utente è occupato.

Indipendentemente dal modo in cui sono configurate le opzioni di occupato, gli utenti di una chiamata o di una conferenza o quelli con una chiamata in attesa non vengono impediti di avviare nuove chiamate o conferenze.

Per altre informazioni sulla funzionalità opzioni occupato, vedere [pianificare le opzioni di occupato per Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Installazione

Verificare di avere installato l'ultima versione di Skype for Business Server e di avere installato la patch più recente. A tale scopo, prima di tutto arrestare tutti i servizi e quindi eseguire il programma di installazione di aggiornamento di Skype for Business Server come indicato di seguito:

1. Eseguire il comando Stop-CsWindowsService.

2. Eseguire il programma di installazione SkypeServerUpdateInstaller. exe su ogni server front-end in un pool.

3. Eseguire il programma di installazione SkypeServerUpdateInstaller. exe in ogni Survivable Branch Server (SBS), se si vuole garantire il supporto per il failover su SBS.

Il programma di installazione distribuirà la versione più recente dell'applicazione Opzioni occupato. Tuttavia, l'applicazione non è abilitata per impostazione predefinita. Per abilitare l'applicazione, eseguire la procedura seguente:

1. Eseguire il cmdlet [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) per abilitare globalmente le opzioni di occupato, come illustrato nell'esempio seguente:

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Se quindi il sito ha un criterio vocale, è necessario abilitare le opzioni di occupato per il criterio vocale, come indicato di seguito:

    Eseguire prima di tutto [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) per recuperare il nome del sito:

   ```powershell
   Get-CsSite
   ```

    Usa il valore Identity (ad esempio: site: Redmond1) recuperato da Get-CsSite per recuperare i criteri vocali del sito nel modo seguente:

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Se per il sito esiste un criterio vocale, eseguire il comando seguente:

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Eseguire quindi il cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) per aggiungere le opzioni di occupato all'elenco delle applicazioni server, come illustrato nell'esempio seguente:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > È necessario sostituire% FQDN% con il nome di dominio completo di un pool specifico.

4. Eseguire quindi il cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) per aggiornare i ruoli di controllo di accesso basati sui ruoli per i cmdlet delle opzioni occupati, come illustrato nell'esempio seguente:

   ```powershell
   Update-CsAdminRole
   ```

5. Infine, avviare i servizi Windows di Skype for Business Server in tutti i server front-end in tutti i pool in cui sono state installate e abilitate le opzioni di occupato eseguendo il comando [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configurare

Per configurare le opzioni di occupato, usare il cmdlet [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .

Ad esempio, il comando seguente configura le opzioni di occupato per l'utente "Ken". In questa configurazione qualsiasi chiamata a "Ken" restituirà un segnale di occupato quando è già in corso una chiamata:

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

Nell'esempio seguente il comando Configura le opzioni di occupato per l'utente "Chrystal Velasquez". In questa configurazione le nuove chiamate in arrivo a "Chrystal Velasquez" verranno inoltrate alla segreteria telefonica quando è già in corso una chiamata:

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Puoi recuperare le informazioni di configurazione sulle opzioni di occupato usando il cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) . L'esempio seguente restituisce l'impostazione delle opzioni di occupato per "KenMyer@Contoso.com":

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

È possibile rimuovere le opzioni di occupato usando il cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) . Il comando seguente rimuove le opzioni di occupato per "Ken":

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Per informazioni dettagliate sui cmdlet usati per configurare le opzioni di occupato, vedere il contenuto di riferimento tecnico per [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)e [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Abilitare la registrazione

Per abilitare la registrazione per le opzioni di occupato tramite il servizio di registrazione centralizzato, specificare quanto segue:

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Verificare e risolvere i problemi

Dopo aver installato le opzioni di occupato, è possibile verificare che l'installazione abbia avuto successo usando il cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) per recuperare l'elenco delle applicazioni server. Se le opzioni di occupato sono installate correttamente, l'output del cmdlet dovrebbe mostrare la configurazione delle opzioni occupate nel modo seguente:

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : http://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

Puoi anche usare il Visualizzatore eventi di Windows per verificare che l'installazione delle opzioni occupato abbia avuto successo e che Skype for Business Server abbia caricato correttamente le opzioni di occupato. Per verificare le opzioni di occupato, aprire il **Visualizzatore eventi-\> registri applicazioni\> e servizi-server Skype (o Lync)** e cercare ID evento = 30253.
