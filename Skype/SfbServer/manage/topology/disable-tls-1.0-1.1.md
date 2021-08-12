---
title: Disabilitare TLS 1.0/1.1 in Skype for Business Server 2015
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
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: Preparare e implementare la disabilitazione di TLS 1.0 e 1.1 negli ambienti.
ms.openlocfilehash: 9bb737466595420770c4374d7d1b76bcc0319e38d188f550fb284b686df7e19f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337774"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Disabilitare TLS 1.0/1.1 in Skype for Business Server 2015

Questo articolo consente di preparare e implementare la disabilitazione di TLS 1.0 e 1.1 negli ambienti. Questo processo richiede una pianificazione e una preparazione approfondite. Esaminare attentamente tutte le informazioni contenute in questo articolo durante la pianificazione della disabilitazione di TLS 1.0 e 1.1 per l'organizzazione. Esistono molte dipendenze esterne e condizioni di connettività che potrebbero essere influenzate dalla disabilitazione di TLS 1.0/1.1, pertanto è garantita una pianificazione e un testing approfonditi.

- [Background e ambito](#background-and-scope)
- [Prerequisiti e processo](#prerequisites-and-process)
- [Scenari di distribuzione avanzati](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a>Background e ambito

I driver principali per fornire TLS 1.0 e 1.1 disabilitano il supporto per Skype for Business Server in locale sono i requisiti del Consiglio degli standard di sicurezza PCI (Payment Card Industry) e degli standard federali per l'elaborazione delle informazioni. Altre informazioni sui requisiti PCI sono disponibili [qui.](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)  Microsoft non può fornire indicazioni sul fatto che l'organizzazione sia o meno necessaria per soddisfare questi o altri requisiti. È necessario determinare se è necessario disabilitare TLS 1.0 e/o 1.1 negli ambienti.

Microsoft ha prodotto un white paper su TLS disponibile qui [e](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)si consiglia anche la lettura in background disponibile in questo blog [Exchange .](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)

## <a name="supportability-scope"></a>Ambito di supporto

*Ambito* si riferisce ai limiti di supportabilità. *Completamente testato e supportato* significa che supportiamo e abbiamo testato la disabilitazione di TLS 1.0 e 1.1 per le versioni del prodotto elencate. *Attualmente in fase di* indagine significa solo questo; stiamo attivamente esaminando l'applicazione di questi prodotti nell'ambito del supporto della disabilitazione TLS. *Fuori ambito* significa che queste versioni del prodotto non supportano la disabilitazione di TLS 1.0 o 1.1 e non funzioneranno, con le eccezioni notate.

### <a name="fully-tested-and-supported-servers"></a>Server completamente testati e supportati

- Skype for Business Server 2019 CU1 17.0.2046.123 (giugno 2019) o versione successiva
- Skype for Business Server 2015 CU9 6.0.9319.548 (maggio 2019) o versione successiva su Windows Server 2012 (con aggiornamento [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) KB o sostituito), 2012 R2 o 2016.
- Aggiornamento sul posto Skype for Business Server 2015, con CU9 6.0.9319.548 (maggio 2019) o versione successiva in Windows Server 2008 R2, 2012 (con aggiornamento [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) KB o sostituito) o 2012 R2.
- Exchange Connettività e Outlook Web App con Exchange Server 2010 SP3 RU19 o versione successiva, indicazioni [qui](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Survivable Branch Appliance (SBA) con Skype for Business Server 2015 CU6 HF2 o versione successiva (confermare al fornitore di aver creato il pacchetto degli aggiornamenti appropriati e di essere stati resi disponibili per il dispositivo)
- Survivable Branch Server (SBS) con Skype for Business Server 2015 CU6 HF2 o versione successiva
- Solo ruolo **Edge** di Lync Server 2013, perché il ruolo Edge non ha una dipendenza da Windows Fabric 1.0.

### <a name="fully-tested-and-supported-clients"></a>Client completamente testati e supportati

- Client desktop Lync 2013 (Skype for Business), MSI e C2R, incluso Basic [15.0.5023.1000 o versione successiva](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 o versione successiva,](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)incluso Basic
- Skype for Business 2016 Fare clic per eseguire Richiedere gli [aggiornamenti di aprile 2018:](/officeupdates/release-notes-office365-proplus) 
    - Mensile e Semi-Annual mirato, 16 \. 0 \. 9126 \. 2152 o superiore
    - Semi-Annual e Deferred Channel, 16 \. 0 \. 8431 \. 2242 o versione successiva
- Skype for Business mac 16.15 o versione successiva
- Skype for Business per iOS e Android 6.19 o versioni successive
- Microsoft Teams Rooms (precedentemente noto come Skype Room System V2 SRS V2) 4.0.64.0 (dicembre 2018) o versione successiva
- Surface Hub per l'edizione del team basata su KB4499162 (maggio 2019, OS Build 15063.1835) o versione successiva
- Skype Web App 2015 CU6 HF2 o versione successiva (fornito con server)

### <a name="currently-being-investigated"></a>Attualmente in fase di analisi

- Call Quality Dashboard (nuova installazione dopo TLS 1.0, 1.1 sono stati disabilitati, vedi sotto)*
 
### <a name="out-of-scope"></a>Esclusioni

Tranne dove specificato, i prodotti seguenti non sono nell'ambito di TLS 1.0/1.1 disabilitano il supporto e non funzioneranno in un ambiente in cui TLS 1.0 e 1.1 sono stati disabilitati. Significato: se si utilizzano ancora server o client fuori ambito, è necessario aggiornarne o rimuoverli se è necessario disabilitare TLS 1.0/1.1 in qualsiasi punto della distribuzione locale di Skype for Business Server.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 o versione inferiore
- Lync per Mac 2011
- Lync 2013 per dispositivi mobili - iOS, iPad, Android o Windows Phone
- Lync "MX" Windows Store client
- Lync Room System (in. k.a. SRSv1). LRS ha raggiunto la fine del supporto il 9 ottobre 2018 e non verrà aggiornato per supportare TLS 1.2.
- Tutti i client Lync 2010
- Lync Telefono Edition - Guida aggiornata [qui](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- Survivable Branch Appliance (SBA) o Survivable Branch Server (SBS) basato su 2013
- Cloud Connector Edition (CCE)
- Skype for Business per Windows Phone

### <a name="exceptions"></a>Eccezioni

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 dipende dalla Windows Fabric versione 1.0.  Nella fase di progettazione di Lync Server 2013, Windows Fabric 1.0 è stato scelto per la sua architettura distribuita accattivante e nuova per fornire replica, disponibilità elevata e tolleranza di errore.  Nel corso del tempo, sia Skype for Business Server che Windows Fabric hanno notevolmente migliorato questa architettura congiunta con una ri-progettazione significativa nelle versioni successive.  Current Skype for Business 2015 Server utilizza Windows Fabric 3.0, ad esempio.

Purtroppo, Windows Fabric 1.0 **non supporta TLS 1.2.  Tuttavia, verrà aggiornato Lync Server 2013 per l'utilizzo con TLS 1.2.** Questo sarà disponibile nel prossimo aggiornamento cumulativo per Lync Server 2013.  Microsoft fornisce il supporto di TLS 1.2 per consentire la coesistenza, la migrazione, la federazione e gli scenari ibridi.

Se l'organizzazione deve disabilitare TLS 1.0 e 1.1 e attualmente si utilizza Lync Server 2013, è consigliabile iniziare il processo di pianificazione, con la possibilità di eseguire l'aggiornamento sul posto o la migrazione side-by-side (nuovi pool, spostare utenti) a Skype for Business Server 2015 o versioni successive.  In caso di problemi, è possibile accelerare la migrazione Skype for Business Online.

#### <a name="call-quality-dashboard"></a>Dashboard Qualità della chiamata

Il dashboard di qualità delle chiamate locali attualmente dipende da TLS 1.0 durante la nuova installazione (prima installazione negli ambienti locali).  Stiamo attualmente esaminando questo problema e si prevede di rilasciare una correzione nel prossimo futuro.  Se si prevede di installare CQD e disabilitare anche TLS 1.0, è consigliabile completare prima l'installazione di CQD e quindi procedere con la disabilitazione di TLS 1.0.

#### <a name="skype-for-business-sdn-manager"></a>Skype for Business SDN Manager

Skype for Business SDN Manager usando SQL database ha una dipendenza da TLS 1.0 durante la nuova installazione. Se si prevede di installare Skype for Business SDN Manager utilizzando SQL un database e disabilitare anche TLS 1.0, è consigliabile completare prima Skype for Business SDN Manager e quindi procedere con la disabilitazione di TLS 1.0. Se TLS 1.0 è stato disabilitato prima dell'installazione, è consigliabile attivare temporaneamente TLS 1.0 nel Skype for Business server back-end SQL Server che verrà utilizzato per ospitare il database di SQL SDN Manager.

#### <a name="third-party-devices"></a>Dispositivi di terze parti

Nei dispositivi di terze parti, ad esempio telefoni 3PIP, videoconferenze, proxy inversi e servizi di bilanciamento del carico, assicurarsi di convalidare la supportabilità di TLS 1.2, testare attentamente e contattare il fornitore, se necessario.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Considerazioni sulla federazione quando si disabilita TLS 1.0/1.1 nei server Perimetrali

È necessario pianificare attentamente e considerare l'impatto della disabilitazione di TLS 1.0/1.1 sui server perimetrali.  Dopo aver disabilitato TLS 1.0 e 1.1, è possibile che altre organizzazioni non siano più in grado di eseguire la federazione con l'organizzazione.

È possibile scegliere di mantenere TLS 1.0/1.1 abilitato nei server Perimetrali per mantenere la compatibilità con le versioni precedenti con sistemi esterni non patch (SfB 2015, Lync 2013) o versioni precedenti (2010).

Microsoft non può fornire consigli o consigli sul fatto che la rete perimetrale (o qualsiasi rete) sia o meno in base agli standard PCI; che deve essere determinato dalla singola società.

Skype for Business Online è in grado di tls 1.2 oggi, quindi non è previsto alcun impatto sulla federazione/ibrida con Online.

PIC (Public IM Connectivity) per Skype consumer: non ci si aspetta che la disabilitazione di TLS 1.0/1.1 influisca sulla [Skype;](../../deploy/deploy-skype-connectivity.md) Microsoft PIC Gateways are already TLS 1.2 capable.

## <a name="prerequisites-and-process"></a>Prerequisiti e processo

Tranne dove indicato in precedenza, una volta che TLS 1.0 e 1.1 sono disabilitati i server fuori ambito, i client e i dispositivi funzioneranno più a lungo correttamente o affatto. Ciò potrebbe significare che è necessario sospendere e attendere le indicazioni aggiornate da Microsoft. Dopo aver soddisfatto tutti i requisiti e avere un piano per risolvere le lacune, procedere.

A un livello elevato, mentre Skype for Business Server 2019 è pronto per la procedura di installazione, Skype for Business Server 2015 richiederà l'installazione di CU9, l'applicazione di aggiornamenti prerequisiti a .NET e SQL, la distribuzione delle chiavi del Registro di sistema prerequisiti e infine un round separato di aggiornamenti della configurazione del sistema operativo (ad esempio, disabilitando TLS 1.0 e 1.1 tramite l'importazione di file del Registro di sistema). È fondamentale completare l'installazione di tutti i prerequisiti, incluso Skype for Business Server 2015 CU6 HF2, prima di disabilitare TLS 1.0 e 1.1 in qualsiasi server dell'ambiente. Ogni Skype for Business server, inclusi i ruoli Edge e SQL back-end, richiede gli aggiornamenti. Assicurarsi inoltre che tutti i client supportati (nell'ambito) siano stati aggiornati alle versioni minime richieste. Non dimenticare di aggiornare anche le workstation di gestione.

Vogliamo seguire il consueto ordine di operazioni di "inside out" per l'aggiornamento Skype for Business server. Trattare i pool di server Director, chat persistente e pool associati come si farebbe normalmente. L'ordine e i metodi per [l'aggiornamento sono descritti qui](topology.md) e [qui](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Processo di alto livello

1. Testare tutti i passaggi del lab prima di configurare i server di produzione.
2. Eseguire il backup e conservare una copia del Registro di sistema esportato in ogni singolo server da aggiornare. Non è possibile condividere registri tra server. contengono chiavi univoche basate sul computer.
3. Aggiornare tutti Skype for Business 2015 a CU9 o versione successiva. Per Skype for Business Server 2019, eseguire l'aggiornamento a CU1 o versione successiva.
4. Installare tutti i prerequisiti in tutti i server.
5. Distribuire le chiavi del Registro di sistema prerequisiti.
6. Verificare che tutti i client nell'ambito siano aggiornati.
7. Disabilitare TLS 1.0 e 1.1 tramite l'importazione del Registro di sistema.
8. Verificare che i carichi di lavoro funzionino come previsto.
    - Se si verificano problemi, risolvere e risolvere i problemi oppure
    - Ripristinare il Registro di sistema dal passaggio 2 per abilitare nuovamente TLS 1.0 e 1.1
9. Verificare che sia in uso solo TLS 1.2.

### <a name="install-prerequisites-to-all-servers"></a>Installare i prerequisiti in tutti i server

Prima di iniziare a disabilitare TLS 1.0 e 1.1 a livello di sistema operativo nelle distribuzioni di Skype for Business Server 2015, è necessario un aggiornamento esteso delle dipendenze. Di seguito sono riportate le versioni minime che possono supportare TLS 1.2. Distribuire tutti gli aggiornamenti dei prerequisiti in Skype for Business server nell'ambiente prima di iniziare a disabilitare TLS 1.0 e 1.1.

- Skype for Business Server 2015 CU9 6.0.9319.548 (maggio 2019) o versione successiva
- [.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) o versione successiva con SchUseStrongCrypto abilitato nel Registro di sistema (fornito di seguito)
- SQL deve essere aggiornato in tutti i server Skype for Business 2015 e back-end. Aggiornare edizione Enterprise pool SQL back-end, quindi le rispettive FE. 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)o versione successiva / SQL Server 2012 SP2 + CU16 o versione successiva / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)o versione successiva / SQL Server 2014 SP2
     - [SQL Server Native Client per SQL Server 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Driver Microsoft ODBC 11 per SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)o versione successiva
     - [Oggetti di gestione condivisi per SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes per SQL server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Passaggi di base per installare i prerequisiti, nell'ordine di operazioni consigliato

1. Installare l'Skype for Business Server CU9 in tutti i server. 
    1. Installare l'aggiornamento ai componenti utilizzando lo strumento di aggiornamento.
    2. Aggiornare i database in base alle procedure documentate. Per Skype for Business Server 2015, vedere KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Convalidare le funzionalità del prodotto nella distribuzione prima di procedere con altre modifiche.
2. Scaricare il programma di installazione offline di .NET 4.7. 
    1. Riferimenti: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Verificare che Skype for Business Server 2015 siano arrestati nel Front End Server.
    3. Riferimenti: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (edizione Standard):```Stop-CsWindowsService```
    5. Ex (edizione Enterprise):```Invoke-CsComputerFailover```
    6. Eseguire il pacchetto del programma di installazione.
    7. Riavviare il server.
3. Aggiornare SQL Express 2014 in tutti i server. 
    1. Riferimenti: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Scaricare SQL 2014 SP2 
        - Riferimenti: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Copiare il supporto di installazione in una cartella sul server (Ad esempio: C:\01_2014SqlSp2)
    4. Verificare Skype for Business Server servizi 2015 siano arrestati nel Front End Server 
        - Ex (edizione Standard):```Stop-CsWindowsService```
        - Ex (edizione Enterprise):```Invoke-CsComputerFailover```
    5. Aprire un prompt dei comandi di amministrazione e aggiornare tutti i componenti e le istanze installati 
        - Esempio: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances
4. Aggiorna SQL Native Client. 
    1. Riferimento: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .
    2. Scarica da [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Verificare Skype for Business Server 2015 i servizi siano arrestati nel Front End Server. 
        - Ex (edizione Standard):```Stop-CsWindowsServices```
        - Ex (edizione Enterprise):```Invoke-CsComputerFailover```
    4. Arrestare l'SQL delle istanze installate 
        - Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (solo edizione Standard):```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Installare l'aggiornamento.
5. Aggiornare odbc Driver 11 per SQL Server includere il supporto per TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).
    1. Scaricare [odbc Driver 11 per SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).
    2. Verificare che Skype for Business Server 2015 siano arrestati nel Front End Server.
        - Esempio (edizione Standard):```Stop-CsWindowsService```
        - Esempio (edizione Enterprise):```Invoke-CsComputerFailover```
    3. Installare l'aggiornamento.
6. Distribuire le chiavi del Registro di sistema prerequisiti.

### <a name="pre-requisite-registry-keys"></a>Chiavi del Registro di sistema prerequisiti

Copiare/incollare il test seguente Blocco note e rinominare TLSPreReq.reg o un nome di propria scelta, quindi importare:

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

Per SQL back-end per edizione Enterprise pool, i prerequisiti e la disabilitazione TLS devono essere considerati come qualsiasi SQL o aggiornamenti del sistema operativo. fare riferimento a:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](./patch-or-update-a-back-end-or-standard-edition-server.md)

Sebbene sia possibile combinare i passaggi di disabilitazione dell'applicazione prerequisito e TLS, è consigliabile applicare tutti i prerequisiti prima di procedere con la disabilitazione di TLS 1.0 e 1.1 a livello di sistema operativo. L'approccio più appropriato consiste nel preparare l'ambiente distribuendo tutti i prerequisiti, convalidando che tutti i carichi di lavoro funzionino correttamente e come previsto e quindi procedendo con la disabilitazione di TLS 1.0/1.1 in un secondo momento.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Disabilitare TLS 1.0 e 1.1 tramite importazione del Registro di sistema

Prima di procedere con i passaggi successivi, assicurarsi di aver completato tutti i prerequisiti e aggiornato *Skype for Business Server*.

Copiare il testo seguente in un file Blocco note e rinominarlo **TLSDisable.reg**:

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

Importare il file reg in ogni server in cui si desidera disabilitare TLS 1.0 e 1.1. Riavviare il server. Una volta che i servizi sono tornati online, passare al server successivo. L'approccio per edizione Enterprise pool è lo stesso da adottare per qualsiasi aggiornamento del sistema operativo.

You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here. Stiamo supportando il riordinamento di Cipher Suite (come mostrato sopra) e la disabilitazione di alcune vecchie crittografia deboli. Questa è la prima volta che sono state supportate ufficialmente queste modifiche a SCHANNEL e Crypto API su Skype for Business Server ed è importante notare che queste modifiche sono le uniche supportate e testate in questo momento. Potremmo considerare configurazioni aggiuntive in futuro, ma per il momento, non modificare il file di importazione del Registro di sistema nell'implementazione.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Verificare che i carichi di lavoro funzionino come previsto

Dopo aver disabilitato TLS 1.0 e 1.1 nell'ambiente, verificare che tutti i carichi di lavoro principali funzionino come previsto, ad esempio presenza di messaggistica istantanea &, chiamate P2P, VoIP aziendale e così via.

**Convalidare solo TLS 1.2 in uso**

Fare in modo che il team di sicurezza eserciti un nuovo controllo del traffico Skype for Business per garantire che i protocolli meno recenti TLS 1.0 e 1.1 non siano più in uso.

In alternativa, puoi usare Internet Explorer per testare le connessioni TLS ai servizi Web da Skype for Business Server 2015 dopo che TLS 1.0 e TLS 1.1 sono stati disabilitati.

1. Avviare Internet Explorer.
2. Selezionare **Strumenti**  >  **Opzioni Internet.**
3. Scegliere la scheda **Avanzate**.
4. In **Impostazioni** scorri verso il basso.
5. Verificare che TLS 1.0, TLS 1.1 e TLS 1.2 siano abilitati.
6. Esplorare l'URL del servizio Web interno del pool SfB 2015 (la connessione deve essere eseguita correttamente).
7. Torna a Internet Explorer e disabilita l'opzione **Usa solo TLS 1.2.**
8. Sfogliare di nuovo l'URL del servizio Web interno del pool SfB 2015 (la connessione non dovrebbe riuscire).

![Opzioni Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Scenari di distribuzione avanzati

Poiché alcuni prerequisiti di dipendenza sono necessari per supportare TLS 1.2 in Skype for Business Server 2015, l'installazione da supporti RTM avrà esito negativo in qualsiasi sistema in cui TLS 1.0 e 1.1 sono stati disabilitati.

**Distribuzione di nuovi edizione Standard Server o pool edizione Enterprise dopo che TLS 1.0 e 1.1 sono stati disabilitati nell'ambiente.**

**Opzione 1:** Utilizzare [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Tieni presente che microsoft sta aggiornando SmartSetup per supportare i file binari SQL aggiornati in un aggiornamento cumulativo futuro e aggiornerà questo articolo in futuro.

**Opzione 2:** Preinstallare istanze SQL locale (RTCLOCAL e LYNCLOCAL)

1. Scaricare e copiare SQL Express 2014 SP2 (SQLEXPR_x64.exe) nella cartella locale in FE. Supponiamo che il percorso della cartella <SQL_FOLDER_PATH>.
2. Avviare PowerShell o il prompt dei comandi e passare a <SQL_FOLDER_PATH>.
3. Creare l'istanza SQL RTCLOCAL eseguendo il comando seguente. Attendere il SQLEXPR_x64.exe termine prima di procedere:Wait until SQLEXPR_x64.exe finishes before proceeding:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati
1. Creare l'istanza SQL LYNCLOCAL eseguendo il comando seguente. Attendere il SQLEXPR_x64.exe termine prima di procedere al passaggio successivo:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic
1. Eseguire Skype for Business Server installazione di RTM 2015.
2. Seguire i passaggi rimanenti della sezione prerequisiti precedente.

**Opzione 3:** È inoltre possibile sostituire manualmente i file binari in una directory multimediale di installazione locale come indicato di seguito:

1. [Installare i prerequisiti per Skype for Business Server](../../deploy/install/install-prerequisites.md)  
2. Installare .NET 4.7: 
      - **Nota:** È stato introdotto il supporto per .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281). Pertanto, nei passaggi successivi di seguito verranno aggiornati i componenti di base prima dell'installazione principale.
      - Download: https://www.microsoft.com/download/details.aspx?id=55167 . 
      - Riferimento: [Software che deve essere installato prima di una Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Copia file/cartelle ISO: 
    - Con l Skype for Business Server ISO 2015 collegato, aprire la directory radice dell'unità collegata come (Ad esempio: D: \) in Esplora file.
    - Copiare tutte le cartelle e i file in una cartella su un disco locale (ad esempio: C:\SkypeForBusiness2015ISO).
    - **Nota:** Prima di installare i componenti, alcuni file dovranno essere aggiornati per il supporto di TLS 1.2.
4. Sostituisci pacchetti MSI/EXE: 
    - Sostituire i pacchetti MSI ed EXE esistenti nella cartella /Setup/amd64/ del supporto di installazione nel computer locale.
    - SQL 2014 SP2 Express:https://www.microsoft.com/download/details.aspx?id=53167 
        - Rinominare il SQLEXPR_x64 nel computer locale e sostituire il file esistente nella cartella Setup/amd64/ del supporto di installazione.
    - SQL Native Client:https://www.microsoft.com/download/details.aspx?id=50402 
        - **Nota:** Se necessario, rinominarlo sqlncli.msi e quindi sostituire il file esistente presente nella cartella Setup/amd64/ del supporto di installazione.
    - SQL Oggetti di gestione:https://www.microsoft.com/download/details.aspx?id=53164 
        - **Nota:** Il Feature Pack include molti elementi che possono essere scaricati. Selezionare questa opzione per SharedManagementObjects.msi download.
        - **Nota:** Sostituire il file esistente presente nella cartella Setup/amd64/ del supporto di installazione.
    - SQL Tipi CLR:https://www.microsoft.com/download/details.aspx?id=53164 
        - **Nota:** Il Feature Pack include molti elementi che possono essere scaricati. Selezionare questa opzione per scaricare CQLSysClrTypes.msi solo
        - **Nota:** sostituire il file esistente presente nella cartella Setup/amd64/ del supporto di installazione.
5. Installare i componenti di base: 
    - Eseguire Setup.exe dalla cartella Setup/amd64/ del supporto di installazione. Seguire le istruzioni per installare i componenti di base
    - Chiudere Componenti di base.
6. Aggiorna componenti di base: 
    - Scarica il programma Skype for Business Update Installer.
    - Eseguire il programma di installazione per aggiornare i componenti di base e installare i contatori delle prestazioni.
    - **Nota:** A data del rilascio di CU6HF2, la funzionalità di aggiornamento automatico attualmente verrà installata solo fino a CU6. Pertanto, lo updater deve essere eseguito separatamente per aggiornare i componenti di base alla versione 6.0.9319.516.
    - Riferimento: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. Installare strumenti di amministrazione (facoltativo): 
    - Verranno installati i tipi CLR di Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) e Microsoft System CLR Types per SQL Server 2014 (x64) utilizzando i file aggiornati. Inoltre, il Skype for Business Server generatore di topologie 2015 e il Pannello di controllo saranno disponibili nel computer locale.
8. Installare l'archivio di configurazione locale (passaggio 1): 
     - Apri la Distribuzione guidata, fai clic su Installa o aggiorna Skype for Business Server sistema e fai clic su **Esegui** al passaggio 1: installare l'archivio di configurazione locale.
     - Fare **clic su** Avanti nella finestra di dialogo Installa archivio di **configurazione** locale.
     ![Finestra di dialogo Installa archivio di configurazione locale](../../media/local-configuration-store.png)
     - Esaminare i risultati e verificare che lo stato dell'attività sia Completato. Esaminare il file di registro risultante facendo clic **su Visualizza registro.**
     ![Lo stato dell'attività viene visualizzato come Completato](../../media/local-configuration-task-completed.png)
     - Fare clic su **Fine**.
9. Configurare o rimuovere Skype for Business Server componenti aggiuntivi (Passaggio 2):
    - Aprire la Distribuzione guidata, fare clic su Installa  o **aggiorna Skype for Business Server Sistema** e fare clic su Esegui al passaggio 2: configurare o rimuovere Skype for Business Server componenti
    - Fare **clic su** Avanti nella finestra di dialogo Skype for Business Server componenti aggiuntivi.
    ![la finestra Configura Skype for Business Server componenti](../../media/set-up-skype-for-business-server-components-window.png)
    - Esaminare il registro utilizzando Visualizza registro e verificare che l'installazione sia stata completata senza problemi. 
    - Fare clic su **Fine**.
10. Procedere con l'installazione e la configurazione aggiuntive in base alle esigenze (a questo punto è possibile riprendere le normali procedure di installazione).