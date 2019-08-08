---
title: Configurare una console Microsoft teams rooms
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Questo articolo descrive come configurare la console Microsoft teams Rooms e le sue periferiche.
ms.openlocfilehash: 1bb1e45eca95628222b799d94c953bb49da1ea17
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243477"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Configurare una console Microsoft teams rooms

Questo articolo descrive come configurare la console Microsoft teams Rooms e le sue periferiche.
  
È consigliabile eseguire questa procedura solo se gli account Microsoft teams o Skype for business e Exchange necessari sono già stati creati e testati come descritto in [distribuire le sale di Microsoft teams](room-systems-v2.md). Sarà necessario l'hardware e il software descritti nei [requisiti di Microsoft teams Rooms](requirements.md). Questo argomento contiene le sezioni seguenti:
  
- [Preparare il supporto di installazione](console.md#Prep_Media)
- [Installare un certificato CA privato nella console](console.md#Certs)
- [Installare Windows 10 e l'app console Microsoft teams rooms](console.md#Reimage)
- [Configurazione iniziale della console](console.md#Initial)
- [Elenco di controllo della distribuzione di Microsoft teams rooms](console.md#Checklist)

> [!NOTE]
> Le sale di Microsoft teams funzionano solo in un ambiente Microsoft teams o Skype for business correttamente configurato in cui gli account di dispositivo sono configurati correttamente, come descritto in [distribuire le sale di Microsoft teams](room-systems-v2.md).
  
## <a name="prepare-the-installation-media"></a>Preparare il supporto di installazione
<a name="Prep_Media"> </a>

L'installazione dell'app console Microsoft teams Rooms richiede un dispositivo di archiviazione USB con almeno 32GB di capacità. Non devono essere presenti altri file nel dispositivo; tutti i file esistenti nello spazio di archiviazione USB andranno perduti.
  
> [!NOTE]
> L'errore di creare il supporto di installazione di Microsoft teams rooms in base a queste istruzioni probabilmente comporterà un comportamento imprevisto.

> [!NOTE]
> Il processo seguente è per la creazione di elementi multimediali di installazione in nuovi dispositivi Microsoft teams rooms. I dispositivi esistenti, per impostazione predefinita, vengono aggiornati automaticamente da Windows Update e Windows Store.
  
1. Scaricare lo [script CreateSrsMedia. ps1](https://go.microsoft.com/fwlink/?linkid=867842).
2. Eseguire lo script CreateSrsMedia. ps1 da una richiesta elevata in un computer con Windows 10.
3. Seguire le istruzioni dello script per creare un disco di configurazione USB di Microsoft teams rooms.


> [!TIP]
> Ogni volta che lo script CreateSrsMedia. ps1 viene avviato, l'output dello schermo includerà il nome di un file di log o una trascrizione per la sessione. In caso di problemi con l'esecuzione dello script, assicurarsi di avere una copia della trascrizione disponibile quando si richiede il supporto. 

Lo script CreateSrsMedia. ps1 automatizza le attività seguenti:

1. Scaricare il programma di installazione MSI più recente per le sale di Microsoft teams.
2. Determinare la build di Windows che l'utente deve fornire. Le versioni rilasciate più di recente possono essere testate e supportate per l'uso con i dispositivi Microsoft teams rooms.
3. Scaricare i componenti di supporto necessari.
4. Assemblare i componenti necessari nel supporto di installazione.

È necessaria una versione specifica di Windows 10 e questa versione è disponibile solo per i clienti con contratti multilicenza.  È possibile ottenere una copia dal [centro servizi per contratti multilicenza](https://www.microsoft.com/Licensing/servicecenter/).

Al termine, rimuovere il disco USB dal computer e procedere con [l'installazione di Windows 10 e dell'app console Microsoft teams Rooms](console.md#Reimage).

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installare Windows 10 e l'app console Microsoft teams rooms
<a name="Reimage"> </a>

È ora necessario applicare il supporto di configurazione creato. Il dispositivo di destinazione verrà eseguito come appliance e l'utente predefinito sarà impostato per eseguire solo l'app console Microsoft teams rooms.

1. Se il dispositivo di destinazione verrà installato in un dock (ad esempio, una superficie Pro), scollegarlo dal Dock.

2. Verificare che il dispositivo di destinazione non sia connesso alla rete.

3. Verificare che il dispositivo di destinazione sia collegato all'alimentazione CA.

4. Collegare il disco di configurazione USB al dispositivo di destinazione.

5. Avviare il disco di configurazione USB. Fare riferimento alle istruzioni del produttore. Se il dispositivo di destinazione è una superficie Pro, usare la procedura seguente per avviare il disco di configurazione USB:

    un. Premere e continuare a tenere premuto il pulsante volume giù (-).

    b. Premere e rilasciare il pulsante di accensione.

    c. Dopo l'avvio della configurazione di Windows, rilasciare il pulsante volume giù (-).

8. Il sistema si arresta dopo il completamento dell'installazione.
    
Dopo che il sistema è stato arrestato, è sicuro rimuovere il disco di configurazione USB. A questo punto, è possibile posizionare il dispositivo di destinazione nel Dock (se si usa un prodotto basato su Dock), allegare le periferiche necessarie per la sala riunioni e connettersi alla rete. Fare riferimento alle istruzioni del produttore.
  
### <a name="selecting-a-language"></a>Selezione di una lingua 

Nell'aggiornamento di Creator è necessario usare lo script ApplyCurrentRegionAndLanguage. ps1 in scenari in cui la selezione della lingua implicita non offre all'utente la lingua effettiva dell'applicazione desiderata (ad esempio, vogliono che l'app console venga aggiornata in francese, ma è in arrivo in inglese).
  
> [!NOTE]
> Le istruzioni seguenti funzionano solo per le console create con l'aggiornamento di Windows Creator. I sistemi legacy/in-Market che non sono stati configurati con il nuovo sistema di provisioning non saranno in grado di usare queste istruzioni, ma dovrebbero anche non risentire del problema iniziale che richiede questo intervento manuale (anniversario Edition consente di selezionare il lingua dell'app in modo esplicito come parte del programma di installazione).
  
### <a name="to-apply-your-desired-language"></a>Per applicare la lingua desiderata

1. Passare alla modalità amministratore.
    
2. Selezionare il menu Start.
    
3. Selezionare l'icona dell'ingranaggio per avviare l'app **Impostazioni** .
    
4. Selezionare **lingua &amp; temporale**.
    
5. Selezionare **lingua &amp; dell'area geografica**.
    
6. Selezionare **Aggiungi una lingua**.
    
7. Selezionare la lingua che si vuole aggiungere.
    
8. Selezionare la lingua appena aggiunta all'elenco "lingue".
    
9. Selezionare **Imposta come predefinito**.
    
10. Per tutte le lingue che si desidera rimuovere:
    
    un. Selezionare la lingua che si vuole rimuovere.
    
    b. Selezionare **Rimuovi**.
    
11. Avviare un prompt dei comandi con privilegi elevati.
    
12. Eseguire il comando seguente: 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. Riavviare il sistema.
    
La lingua desiderata viene ora applicata alla console Microsoft teams rooms.
## <a name="initial-set-up-of-the-console"></a>Configurazione iniziale della console
<a name="Initial"> </a>

Dopo l'installazione di Windows, l'app console Microsoft teams Rooms verrà inserita nel processo di configurazione iniziale quando verrà avviata la successiva o se è stata selezionata l'opzione/reboot.
  
1. Viene visualizzata la schermata dell'account utente. Immettere l'indirizzo di accesso Skype (in formato utente @ dominio) dell'account della sala da usare con la console.
    
2. Immettere la password per l'account della sala e immetterla di nuovo per verificarla.
    
3. In "Configura dominio" impostare il nome di dominio completo per Skype for Business Server. Se il dominio SIP di Skype for business è diverso dal dominio Exchange dell'utente, immettere il dominio Exchange in questo campo.
    
4. Fare clic su **Avanti**.
    
5. Selezionare i dispositivi indicati nella schermata caratteristiche e fare clic su **Avanti**. Il valore predefinito consiste nel fatto che la condivisione dello schermo automatico sia impostata su attivato e nascondere i nomi delle riunioni impostati su disattivato. I dispositivi da selezionare sono:
    
   - Microfono per i servizi di conferenza: il microfono predefinito per questa sala riunioni.
    
   - Altoparlante per i servizi di conferenza: altoparlante predefinito per i servizi di conferenza. 
    
   - Altoparlante predefinito: l'altoparlante usato per l'audio dall'uso di HDMI.
    
     Ogni elemento ha un menu a discesa di opzioni tra cui scegliere. Devi effettuare una selezione per ogni dispositivo.
    
6. Fare clic su **fine**.
    
L'app console Microsoft teams Rooms dovrebbe iniziare immediatamente l'accesso a Skype for Business Server con le credenziali immesse sopra e deve anche iniziare a sincronizzare il calendario con Exchange usando le stesse credenziali. Per informazioni dettagliate sull'uso dell'app console, vedere la [Guida di Microsoft teams Rooms](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Microsoft teams Rooms si basa sulla presenza di hardware console certificato. Anche un'immagine creata correttamente che contiene l'app console Microsoft teams Rooms non verrà avviata oltre la procedura di configurazione iniziale, a meno che non venga rilevato l'hardware della console. Per le soluzioni basate su Surface Pro, la superficie Pro deve essere connessa all'hardware Dock associato per superare questo controllo.
  
> [!NOTE]
> Alcuni utenti di lingua diversa dall'inglese potrebbero avere bisogno di una tastiera fisica connessa alla console durante la configurazione iniziale, se i simboli non sono supportati nella tastiera virtuale.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installare un certificato CA privato nella console
<a name="Certs"> </a>

La console Microsoft teams Rooms deve considerare attendibile i certificati usati dai server a cui si connette. Per Office 365, questa operazione viene eseguita automaticamente, poiché questi server usano le autorità di certificazione pubbliche e questi vengono automaticamente considerati attendibili da Windows 10. Nel caso in cui l'autorità di certificazione sia privata, ad esempio una distribuzione locale con Active Directory e l'autorità di certificazione di Windows, è possibile aggiungere il certificato alla console Microsoft teams rooms in un paio di modi:
  
- È possibile accedere alla console in Active Directory e aggiungere automaticamente i certificati necessari, poiché l'autorità di certificazione viene pubblicata in Active Directory (opzione di distribuzione normale).
    
- È possibile installare manualmente il certificato dopo il processo di imaging. Prima di eseguire questa operazione, è necessario completare [la configurazione iniziale della console](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>Per installare manualmente il certificato

1. Scaricare il certificato CA nel computer e salvarlo in "C:\Skype room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Posizionare la console in modalità amministratore (vedere [modalità di amministrazione e gestione dei dispositivi](room-systems-v2-operations.md#AdminMode)).
    
3. Eseguire il comando seguente:
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Partecipare a un dominio Active Directory (facoltativo)
<a name="Certs"> </a>

È possibile partecipare alle console di Microsoft teams Rooms al proprio dominio. Le console di Microsoft teams Rooms devono essere posizionate in un'unità organizzativa separata dalle workstation PC perché molti criteri di workstation non sono compatibili con le sale di Microsoft teams. Un esempio comune sono i criteri di applicazione delle password che impediscono l'avvio automatico delle sale di Microsoft teams. Per informazioni sulla gestione delle impostazioni degli oggetti Criteri di gruppo, vedere [gestire le sale di Microsoft teams](room-systems-v2-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Per partecipare a Microsoft teams Rooms a un dominio

1. Accedere alla console dall'account di amministrazione (vedere [modalità di amministrazione e gestione dei dispositivi](room-systems-v2-operations.md#AdminMode)).
    
2. Avviare il prompt dei comandi di PowerShell con privilegi elevati.
    
3. Immettere il comando seguente in PowerShell:
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Ad esempio, se il dominio completo è redmond.corp.microsoft.com e si vuole che le console di Microsoft teams Rooms si trovino in un'unità organizzativa "Microsoft teams Rooms" che è un elemento figlio di un'unità organizzativa "Resources", il comando sarà:
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Se si vuole rinominare il computer quando si partecipa a un dominio, usare il contrassegno-NewName seguito dal nuovo nome del computer.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Elenco di controllo della distribuzione di Microsoft teams rooms
<a name="Checklist"> </a>

Usare l'elenco di controllo seguente durante una verifica finale che la console e tutte le sue periferiche siano completamente configurate:
  
**Impostazioni applicazione**

|||
|:-----|:-----|
|☐  <br/> |Nome account della sala e telefono # (se PSTN abilitato) vengono visualizzati correttamente nella parte superiore destra della schermata della console  <br/> |
|☐  <br/> |Il nome del computer Windows è impostato correttamente (utile per l'amministrazione remota)  <br/> |
|☐  <br/> |Password dell'account amministratore impostata e verificata  <br/> |
|☐  <br/> |Tutti gli aggiornamenti del firmware sono stati applicati  <br/> |
   
**Periferiche audio/video**

|||
|:-----|:-----|
|☐  <br/> |La versione del firmware della periferica fotocamera è corretta (se applicabile)  <br/> |
|☐  <br/> |Fotocamera funzionale e posizionata in modo ottimale  <br/> |
|☐  <br/> |Impostazioni per il dispositivo predefinito per la riproduzione e la riproduzione del dispositivo di comunicazione predefinito impostato su periferica audio desiderata  <br/> |
|☐  <br/> |Impostazioni per la registrazione del dispositivo di comunicazione predefinito impostato sulla periferica audio desiderata  <br/> |
|☐  <br/> |La versione del firmware della periferica audio è corretta (se applicabile)  <br/> |
|☐  <br/> |Dispositivo di input audio funzionale e posizionato in modo ottimale  <br/> |
|☐  <br/> |Dispositivo di output audio funzionale e posizionato in modo ottimale  <br/> |
   
**Dock**

|||
|:-----|:-----|
|☐  <br/> |I cavi sono sicuri e non vengono pizzicati  <br/> |
|☐  <br/> |L'acquisizione di audio tramite HDMI è funzionale  <br/> |
|☐  <br/> |L'acquisizione di video tramite HDMI è funzionale  <br/> |
|☐  <br/> |Il Dock può ruotare liberamente  <br/> |
|☐  <br/> |La luminosità dello schermo è accettabile per l'ambiente  <br/> |
   
## <a name="see-also"></a>Vedere anche
<a name="Checklist"> </a>

[Pianificare le sale di Microsoft Teams](skype-room-systems-v2-0.md)
  
[Distribuire le sale di Microsoft Teams](room-systems-v2.md)
  
[Configurare una console Microsoft teams rooms](console.md)
  
[Gestire le sale di Microsoft Teams](skype-room-systems-v2.md)
