---
title: Configurare una console per Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Questo articolo descrive come configurare la console di Microsoft Teams Rooms e le relative periferiche.
ms.openlocfilehash: 4caa2677eea01ecc96e426692b536aec8563c473
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117574"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Configurare una console per Microsoft Teams Rooms

Questo articolo descrive come configurare la console di Microsoft Teams Rooms e le relative periferiche.
  
È consigliabile eseguire questa procedura solo se gli account necessari di Microsoft Teams o Skype for Business ed Exchange sono già stati creati e testati come descritto in Distribuire le chat room [di Microsoft Teams.](rooms-deploy.md) Sono necessari l'hardware e il software descritti nei [requisiti di Microsoft Teams Rooms.](requirements.md) Questo argomento contiene le sezioni seguenti:
  
- [Preparare il supporto di installazione](console.md#Prep_Media)
- [Installare un certificato CA privato nella console](console.md#Certs)
- [Installare Windows 10 e l'app console Microsoft Teams Rooms](console.md#Reimage)
- [Configurazione iniziale della console](console.md#Initial)
- [Elenco di controllo per la distribuzione di Microsoft Teams Rooms](console.md#Checklist)

> [!NOTE]
> Le chat room di Microsoft Teams funzionano solo in un ambiente Microsoft Teams o Skype for Business correttamente configurato in cui gli account del dispositivo sono configurati correttamente, come descritto in [Distribuire le sale di Microsoft Teams.](rooms-deploy.md)
  
## <a name="prepare-the-installation-media"></a>Preparare il supporto di installazione
<a name="Prep_Media"> </a>

L'installazione dell'app console Microsoft Teams Rooms richiede un dispositivo di archiviazione USB con almeno 32 GB di capacità. Nel dispositivo non dovrebbero essere presenti altri file. i file esistenti sullo spazio di archiviazione USB andranno persi.
  
> [!NOTE]
> Se non si crea il supporto di installazione di Microsoft Teams Rooms in base a queste istruzioni, è probabile che si crei un comportamento imprevisto.

> [!NOTE]
> Il processo seguente è per la creazione di supporti di installazione per l'immagine di nuovi dispositivi Microsoft Teams Rooms. I dispositivi esistenti, per impostazione predefinita, vengono aggiornati automaticamente da Windows Update e Windows Store.

> [!IMPORTANT]
> Il computer Windows 10 usato per creare il supporto di installazione di Microsoft Teams Rooms deve essere nella stessa versione o versione successiva di Windows del supporto di installazione di destinazione.
  
1. Scaricare lo [scriptCreateSrsMedia.ps1 .](https://go.microsoft.com/fwlink/?linkid=867842)
2. Eseguire lo script CreateSrsMedia.ps1 da un prompt con privilegi elevati in un computer Windows 10.
3. Seguire le istruzioni dello script per creare un disco di configurazione USB di Microsoft Teams Rooms.


> [!TIP]
> Ogni volta che lo script CreateSrsMedia.ps1, l'output dello schermo includerà il nome di un file di log o di una trascrizione per la sessione. In caso di problemi con l'esecuzione dello script, assicurarsi di avere una copia della trascrizione disponibile quando si richiede il supporto. 

Lo script CreateSrsMedia.ps1 automatizza le attività seguenti:

1. Scaricare il programma di installazione MSI più recente per Microsoft Teams Rooms.
2. Determinare la build di Windows che l'utente deve fornire. Le versioni rilasciate più di recente possono essere testate e supportate per l'uso con i dispositivi Microsoft Teams Rooms.
3. Scaricare i componenti di supporto necessari.
4. Assemblare i componenti necessari sul supporto di installazione.

È necessaria una versione specifica di Windows 10 e questa versione è disponibile solo per i clienti con contratto multilicenza.  È possibile ottenere una copia dal [Centro servizi per contratti multilicenza.](https://www.microsoft.com/Licensing/servicecenter/)

Al termine, rimuovere il disco USB dal computer e passare a [Installare Windows 10 e l'app console Microsoft Teams Rooms.](console.md#Reimage)

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installare Windows 10 e l'app console Microsoft Teams Rooms
<a name="Reimage"> </a>

A questo punto è necessario applicare il supporto di configurazione creato. Il dispositivo di destinazione verrà eseguito come appliance e l'utente predefinito verrà impostato in modo da eseguire solo l'app console Microsoft Teams Rooms.

1. Se il dispositivo di destinazione verrà installato in un dock (ad esempio un Surface Pro), scollegarlo dal dock.

2. Verificare che il dispositivo di destinazione non sia connesso alla rete.

3. Verificare che il dispositivo di destinazione sia connesso all'alimentazione CA.

4. Collegare il disco di configurazione USB al dispositivo di destinazione.

5. Eseguire l'avvio sul disco di configurazione USB. Fare riferimento alle istruzioni del produttore. Se il dispositivo di destinazione è un Surface Pro, eseguire la procedura seguente per eseguire l'avvio nel disco di configurazione USB:

    a. Premere e continuare a tenere premuto il pulsante del volume (-).

    b. Premere e rilasciare il pulsante di alimentazione.

    c. Dopo l'avvio dell'installazione di Windows, rilasciare il pulsante del volume verso il basso (-).

8. Il sistema verrà arrestato al termine dell'installazione.
    
Dopo l'arresto del sistema, è possibile rimuovere il disco di configurazione USB. A questo punto, è possibile posizionare il dispositivo di destinazione nel dock (se si usa un prodotto basato su dock), collegare le periferiche necessarie per la sala riunioni e connettersi alla rete. Fare riferimento alle istruzioni del produttore.

> [!NOTE]
> Gli aggiornamenti software per Microsoft Teams Rooms vengono scaricati automaticamente da Microsoft Store per le aziende. Vedere [Prerequisiti per Microsoft Store per le aziende](/microsoft-store/prerequisites-microsoft-store-for-business) e l'istruzione per verificare che la console della sala sia in grado di accedere al negozio e di eseguire l'aggiornamento automatico.  

### <a name="selecting-a-language"></a>Selezione di una lingua 

In Creator's Update, è necessario usare lo script ApplyCurrentRegionAndLanguage.ps1 in scenari in cui la selezione implicita della lingua non fornisce all'utente la lingua effettiva dell'applicazione desiderata(ad esempio, vuole che l'app console sia disponibile in francese, ma sarà disponibile in inglese).
  
> [!NOTE]
> Le istruzioni seguenti funzionano solo per le console create con Windows Creator's Update. I sistemi legacy/in-market che non sono stati impostati usando i supporti multimediali con il nuovo sistema di provisioning non potranno usare queste istruzioni, ma non dovranno risentire del problema iniziale che richiede questo intervento manuale (Anniversary Edition consente di scegliere esplicitamente la lingua dell'app nell'ambito della configurazione).
  
### <a name="to-apply-your-desired-language"></a>Per applicare la lingua desiderata

1. Passare alla modalità di amministrazione.
    
2. Selezionare il menu Start.
    
3. Seleziona l'icona a forma di ingranaggio per avviare **l'app** Impostazioni.
    
4. Selezionare **Lingua &amp; ora**.
    
5. Selezionare **Lingua &amp; area geografica.**
    
6. Selezionare **Aggiungi una lingua.**
    
7. Selezionare la lingua da aggiungere.
    
8. Selezionare la lingua appena aggiunta all'elenco "Lingue".
    
9. Selezionare **Imposta come predefinito.**
    
10. Per le lingue da rimuovere:
    
    a. Selezionare la lingua da rimuovere.
    
    b. Selezionare **Rimuovi**.
    
11. Avviare un prompt dei comandi con privilegi elevati.
    
12. Eseguire il comando seguente: 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. Riavviare il sistema.
    
La lingua desiderata viene ora applicata alla console di Microsoft Teams Rooms.
## <a name="initial-set-up-of-the-console"></a>Configurazione iniziale della console
<a name="Initial"> </a>

Dopo l'installazione di Windows, l'app console Microsoft Teams Rooms verrà avviata nel processo di configurazione iniziale all'avvio successivo o se è stata scelta l'opzione /reboot.
  
1. Viene visualizzata la schermata Account utente. Immetti l'indirizzo di accesso Skype (in user@domain) dell'account della chat room da usare con la console.
    
2. Immettere la password per l'account della chat room e immetterla di nuovo per verificarla.
    
3. In "Configura dominio", impostare l'FQDN per Skype for Business Server. Se il dominio SIP di Skype for Business è diverso dal dominio di Exchange dell'utente, immettere il dominio di Exchange in questo campo.
    
4. Fare clic su **Avanti**.
    
5. Selezionare i dispositivi indicati nella schermata Caratteristiche e fare clic su **Avanti.** Per impostazione predefinita, la condivisione automatica dello schermo è impostata su Su e Nascondi nomi riunione su Disattivato. I dispositivi da selezionare sono:
    
   - Microfono per conferenze: il microfono predefinito per questa sala riunioni.
    
   - Altoparlante per conferenza: l'altoparlante predefinito per le conferenze. 
    
   - Altoparlante predefinito: l'altoparlante usato per l'audio dall'ingestione HDMI.
    
     Ogni elemento ha un menu a discesa di opzioni tra cui selezionare. È necessario effettuare una selezione per ogni dispositivo.
    
6. Fare clic **su Fine.**
    
L'app console Microsoft Teams Rooms dovrebbe iniziare immediatamente ad accedere a Skype for Business Server con le credenziali immesse sopra e dovrebbe anche iniziare a sincronizzare il calendario con Exchange usando le stesse credenziali. Per informazioni dettagliate sull'uso dell'app console, vedere la Guida di [Microsoft Teams Rooms.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)
  
> [!IMPORTANT]
> Microsoft Teams Rooms si basa sulla presenza di hardware della console certificato. Anche un'immagine creata correttamente contenente l'app console Microsoft Teams Rooms non verrà avviato oltre la procedura di configurazione iniziale, a meno che non venga rilevato l'hardware della console. Per le soluzioni basate su Surface Pro, Surface Pro deve essere connesso all'hardware del dock di accompagnamento per superare questo controllo.
  
> [!NOTE]
> Alcuni utenti di lingue non inglesi potrebbero aver bisogno di una tastiera fisica connessa alla console durante la configurazione iniziale nel caso in cui i simboli non siano supportati sulla tastiera virtuale.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installare un certificato CA privato nella console
<a name="Certs"> </a>

La console di Microsoft Teams Rooms deve considerare attendibili i certificati usati dai server a cui si connette. Per O365 questa operazione viene eseguita automaticamente, poiché questi server usano autorità di certificazione pubbliche, che vengono automaticamente considerati attendibili da Windows 10. In un caso in cui l'Autorità di certificazione sia privata, ad esempio una distribuzione locale con Active Directory e l'Autorità di certificazione di Windows, è possibile aggiungere il certificato alla console di Microsoft Teams Rooms in un paio di modi:
  
- È possibile aggiungere la console ad Active Directory e aggiungere automaticamente i certificati necessari in base alla pubblicazione dell'Autorità di certificazione in Active Directory (opzione di distribuzione normale).
    
- È possibile installare il certificato manualmente dopo il processo di creazione di immagini. Prima di eseguire questa operazione, è necessario [completare la configurazione iniziale della console.](console.md#Initial)
    
### <a name="to-manually-install-the-certificate"></a>Per installare manualmente il certificato

1. Scaricare il certificato CA nel computer e salvarlo in "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Posizionare la console in modalità di amministrazione (vedere [Modalità di amministrazione e gestione dei dispositivi).](rooms-operations.md#AdminMode)
    
3. Eseguire il comando seguente:
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Aggiunta a un dominio di Active Directory (facoltativo)
<a name="Certs"> </a>

È possibile aggiungere le console di Microsoft Teams Rooms al dominio. Le console di Microsoft Teams Rooms devono essere collocate in un'unità organizzativa separata dalle workstation del PC, perché molti criteri per le workstation non sono compatibili con Microsoft Teams Rooms. Un esempio comune sono i criteri di applicazione delle password che impediscono l'avvio automatico di Microsoft Teams Rooms. Per informazioni sulla gestione delle impostazioni dell'oggetto Criteri di gruppo, vedere [Gestire le chat room di Microsoft Teams.](rooms-operations.md)
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Per aggiungere le chat room di Microsoft Teams a un dominio

1. Accedere alla console dall'account di amministratore (vedere [Modalità di amministrazione e gestione dei dispositivi).](rooms-operations.md#AdminMode)
    
2. Avviare il prompt dei comandi di Powershell con privilegi elevati.
    
3. Immettere il comando seguente in Powershell:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Ad esempio, se il dominio completo è redmond.corp.microsoft.com e si vuole che le console di Microsoft Teams Rooms siano in un'unità organizzativa "Microsoft Teams Rooms" figlio di un'unità organizzativa "Risorse", il comando sarà:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Se si vuole rinominare il computer quando lo si unisce a un dominio, usare il flag -NewName seguito dal nuovo nome del computer.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Elenco di controllo per la distribuzione di Microsoft Teams Rooms
<a name="Checklist"> </a>

Usare l'elenco di controllo seguente durante una verifica finale che la console e tutte le relative periferiche siano completamente configurate:
  
**Impostazioni dell'applicazione**

|||
|:-----|:-----|
|☐  <br/> |Il nome dell'account della sala e il numero di telefono (se PSTN abilitato) vengono visualizzati correttamente nell'angolo in alto a destra dello schermo della console  <br/> |
|☐  <br/> |Il nome del computer Windows è impostato correttamente (utile per l'amministrazione remota)  <br/> |
|☐  <br/> |Password dell'account amministratore impostata e verificata  <br/> |
|☐  <br/> |Tutti gli aggiornamenti del firmware sono stati applicati  <br/> |
   
**Periferiche audio/video**

|||
|:-----|:-----|
|☐  <br/> |La versione del firmware delle periferiche della fotocamera è corretta (se applicabile)  <br/> |
|☐  <br/> |Fotocamera funzionale e posizionata in modo ottimale  <br/> |
|☐  <br/> |Impostazioni per Dispositivo di riproduzione predefinito e Dispositivo di comunicazione predefinito riproduzione impostato sulla periferica audio prevista  <br/> |
|☐  <br/> |Impostazioni per registrazione dispositivo di comunicazione predefinito impostato sulla periferica audio prevista  <br/> |
|☐  <br/> |La versione del firmware delle periferiche audio è corretta (se applicabile)  <br/> |
|☐  <br/> |Dispositivo di input audio funzionale e posizionato in modo ottimale  <br/> |
|☐  <br/> |Dispositivo di output audio funzionante e posizionato in modo ottimale  <br/> |
   
**Dock**

|||
|:-----|:-----|
|☐  <br/> |I cavi sono sicuri e non pizzicati  <br/> |
|☐  <br/> |L'inserimento audio tramite HDMI è funzionale  <br/> |
|☐  <br/> |L'inserimento di video su HDMI è funzionale  <br/> |
|☐  <br/> |Il Dock può ruotare liberamente  <br/> |
|☐  <br/> |La luminosità dello schermo è accettabile per l'ambiente  <br/> |
   
## <a name="see-also"></a>Vedere anche
<a name="Checklist"> </a>

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).