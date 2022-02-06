---
title: Installare e configurare opzioni di disponibilità per Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - Strat_SB_Admin
ms.custom: null
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Informazioni su come installare e configurare le opzioni occupato in Skype for Business Server.
---

# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Installare e configurare opzioni di disponibilità per Skype for Business Server

Informazioni su come installare e configurare le opzioni occupato in Skype for Business Server.

Opzioni occupato è un nuovo criterio vocale introdotto nell'aggiornamento cumulativo di luglio 2016 che consente di configurare la modalità di gestione delle chiamate in arrivo quando un utente è già in una chiamata o una conferenza o ha una chiamata in attesa. Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica.

Se per l'organizzazione è abilitata l'opzione Opzioni occupato, tutti gli utenti del Enterprise, sia VoIP aziendale che non VoIP aziendale, possono utilizzare le opzioni di configurazione seguenti:

- Occupato su occupato - In cui le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato se l'utente è occupato.

- Segreteria telefonica su Occupato - In cui le nuove chiamate in arrivo verranno inoltrate alla segreteria telefonica se l'utente è occupato.

Indipendentemente dalla configurazione delle opzioni di disponibilità, agli utenti di una chiamata o di una conferenza o a quelli con una chiamata in attesa non viene impedito di avviare nuove chiamate o conferenze.

Per ulteriori informazioni sulla funzionalità Opzioni occupato, vedere [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Installare

Assicurarsi di avere installato la versione più recente di Skype for Business Server e di aver installato la patch più recente. A tale scopo, arrestare prima tutti i servizi ed eseguire il programma di Skype for Business Server di aggiornamento come indicato di seguito:

1. Eseguire il Stop-CsWindowsService comando.

2. Eseguire il SkypeServerUpdateInstaller.exe di installazione in ogni Front End Server di un pool.

3. Eseguire il SkypeServerUpdateInstaller.exe su ogni Survivable Branch Server (SBS), se si desidera garantire il supporto per il failover in SBS.

Il programma di installazione distribuirà la versione più recente dell'applicazione Opzioni occupato. Tuttavia, l'applicazione non è abilitata per impostazione predefinita. Per abilitare l'applicazione, eseguire la procedura seguente:

1. Eseguire il cmdlet [Set-CsVoicePolicy](/powershell/module/skype/set-csvoicepolicy?view=skype-ps) per abilitare globalmente le opzioni di occupato, come illustrato nell'esempio seguente:

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Successivamente, se il sito dispone di un criterio vocale, è necessario abilitare Opzioni occupato per il criterio vocale come segue:

    Eseguire innanzitutto [Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps) per recuperare il nome del sito:

   ```powershell
   Get-CsSite
   ```

    Utilizzare il valore Identity (ad esempio: Site:Redmond1) recuperato da Get-CsSite per recuperare i criteri vocali del sito come segue:

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Se esiste un criterio vocale per il sito, eseguire il comando seguente:

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Eseguire quindi il cmdlet [New-CsServerApplication](/powershell/module/skype/new-csserverapplication?view=skype-ps) per aggiungere opzioni di disponibilità all'elenco delle applicazioni server, come illustrato nell'esempio seguente:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > È necessario sostituire %FQDN% con il nome di dominio completo di un pool specifico.

4. Eseguire quindi il cmdlet [Update-CsAdminRole](/powershell/module/skype/update-csadminrole?view=skype-ps) per aggiornare i ruoli RBAC (Role-Based Access Control) per i cmdlet Opzioni occupato, come illustrato nell'esempio seguente:

   ```powershell
   Update-CsAdminRole
   ```

5. Infine, avviare i Skype for Business Server Windows in tutti i Front End Server in tutti i pool in cui è stato installato e abilitato Opzioni occupato eseguendo il [comando Start-CsWindowsService](/powershell/module/skype/start-cswindowsservice?view=skype-ps):

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configurazione

Per configurare le opzioni occupato, utilizzare il cmdlet [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .

Ad esempio, il comando seguente configura le opzioni di occupato per l'utente "Davide Garghentini". In questa configurazione, qualsiasi chiamata a "Ken Myer" restituirà un segnale di occupato quando è già in una chiamata:

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

Nell'esempio successivo, il comando configura le opzioni di occupato per l'utente "Cristal Velasquez". In questa configurazione, le nuove chiamate in arrivo a "Cristal Velasquez" verranno inoltrate alla segreteria telefonica quando è già in una chiamata:

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

È possibile recuperare informazioni di configurazione sulle opzioni di disponibilità utilizzando il cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) . Nell'esempio seguente viene restituita l'impostazione Opzioni occupato per "KenMyer@Contoso.com":

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

È possibile rimuovere opzioni occupato utilizzando il cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) . Il comando seguente consente di rimuovere le opzioni di occupato per "Ken Myer":

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Per informazioni dettagliate sui cmdlet utilizzati per configurare le opzioni occupato, vedere il contenuto di riferimento tecnico per [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) e [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Abilitare la registrazione

Per abilitare la registrazione per le opzioni di occupato utilizzando il servizio di registrazione centralizzata, specificare quanto segue:

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Verificare e risolvere i problemi

Dopo aver installato Opzioni occupato, è possibile verificare che l'installazione sia stata eseguita correttamente utilizzando il cmdlet [Get-CsServerApplication](/powershell/module/skype/get-csserverapplication?view=skype-ps) per recuperare l'elenco delle applicazioni server. Se opzioni occupato è installato correttamente, l'output del cmdlet dovrebbe mostrare la configurazione opzioni occupato come segue:

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

È inoltre possibile utilizzare Windows visualizzatore eventi per verificare che l'installazione di Opzioni occupato sia stata eseguita correttamente e che Skype for Business Server le opzioni occupato siano state caricate correttamente. Per verificare le opzioni occupato, aprire Visualizzatore eventi **-\> Registri applicazioni e servizi -\> Skype (o Lync) Server** e cercare ID evento = 30253.