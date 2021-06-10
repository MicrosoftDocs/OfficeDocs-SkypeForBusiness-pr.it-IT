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
  
È consigliabile eseguire questa procedura solo se gli account Microsoft Teams o Skype for Business e Exchange necessari sono già stati creati e testati come descritto in [Distribuire Microsoft Teams Rooms](rooms-deploy.md). Sono necessari l'hardware e il software descritti in Microsoft Teams Rooms [requisiti.](requirements.md) Questo argomento contiene le sezioni seguenti:
  
- [Preparare il supporto di installazione](console.md#Prep_Media)
- [Installare un certificato CA privato nella console](console.md#Certs)
- [Installare Windows 10 e l'app Microsoft Teams Rooms console](console.md#Reimage)
- [Configurazione iniziale della console](console.md#Initial)
- [Microsoft Teams Rooms di distribuzione](console.md#Checklist)

> [!NOTE]
> Microsoft Teams Rooms funziona solo in un ambiente Microsoft Teams o Skype for Business in cui gli account dei dispositivi sono configurati correttamente, come descritto in Distribuire [Microsoft Teams Rooms](rooms-deploy.md).
  
## <a name="prepare-the-installation-media"></a>Preparare il supporto di installazione
<a name="Prep_Media"> </a>

L'installazione dell'app Microsoft Teams Rooms console richiede un dispositivo di archiviazione USB con almeno 32 GB di capacità. Nel dispositivo non dovrebbero essere presenti altri file. i file esistenti sullo spazio di archiviazione USB andranno persi.
  
> [!NOTE]
> Se non si crea il Microsoft Teams Rooms di installazione in base a queste istruzioni, è probabile che si crei un comportamento imprevisto.

> [!NOTE]
> Il processo seguente consente di creare supporti di installazione per immagini di Microsoft Teams Rooms dispositivi. I dispositivi esistenti, per impostazione predefinita, vengono aggiornati automaticamente da Windows Update e Windows Store.

> [!IMPORTANT]
> Il Windows 10 usato per creare il supporto di Microsoft Teams Rooms di installazione deve essere nella stessa o versione successiva di Windows come supporto di installazione di destinazione.
  
1. Scaricare lo [scriptCreateSrsMedia.ps1 .](https://go.microsoft.com/fwlink/?linkid=867842)
2. Eseguire lo script CreateSrsMedia.ps1 da un prompt con privilegi elevati in un Windows 10 computer.
3. Seguire le istruzioni dello script per creare un disco Microsoft Teams Rooms di configurazione USB.


> [!TIP]
> Ogni volta che lo script CreateSrsMedia.ps1, l'output dello schermo includerà il nome di un file di log o di una trascrizione per la sessione. In caso di problemi con l'esecuzione dello script, assicurarsi di avere una copia della trascrizione disponibile quando si richiede il supporto. 

Lo script CreateSrsMedia.ps1 automatizza le attività seguenti:

1. Scaricare il programma di installazione MSI più recente per Microsoft Teams Rooms.
2. Determinare la build di Windows che l'utente deve fornire. Le versioni rilasciate più di recente possono essere testate e supportate per l'uso con Microsoft Teams Rooms dispositivi.
3. Scaricare i componenti di supporto necessari.
4. Assemblare i componenti necessari sul supporto di installazione.

È necessaria una versione specifica Windows 10 e questa versione è disponibile solo per i clienti con contratto multilicenza.  È possibile ottenere una copia dal [Centro servizi per contratti multilicenza.](https://www.microsoft.com/Licensing/servicecenter/)

Al termine, rimuovere il disco USB dal computer e passare a Installa [Windows 10 e all'app Microsoft Teams Rooms console.](console.md#Reimage)

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installare Windows 10 e l'app Microsoft Teams Rooms console
<a name="Reimage"> </a>

A questo punto è necessario applicare il supporto di configurazione creato. Il dispositivo di destinazione verrà eseguito come appliance e l'utente predefinito sarà impostato in modo da eseguire solo l'app Microsoft Teams Rooms console.

1. Se il dispositivo di destinazione verrà installato in un dock (ad esempio un Surface Pro), scollegarlo dal dock.

2. Verificare che il dispositivo di destinazione non sia connesso alla rete.

3. Verificare che il dispositivo di destinazione sia connesso all'alimentazione CA.

4. Collegare il disco di configurazione USB al dispositivo di destinazione.

5. Eseguire l'avvio sul disco di configurazione USB. Fare riferimento alle istruzioni del produttore. Se il dispositivo di destinazione è Surface Pro, eseguire la procedura seguente per eseguire l'avvio nel disco di configurazione USB:

    a. Premere e continuare a tenere premuto il pulsante del volume (-).

    b. Premere e rilasciare il pulsante di alimentazione.

    c. Dopo Windows l'avvio dell'installazione, rilasciare il pulsante volume verso il basso (-).

8. Il sistema verrà arrestato al termine dell'installazione.
    
Dopo l'arresto del sistema, è possibile rimuovere il disco di configurazione USB. A questo punto, è possibile posizionare il dispositivo di destinazione nel dock (se si usa un prodotto basato su dock), collegare le periferiche necessarie per la sala riunioni e connettersi alla rete. Fare riferimento alle istruzioni del produttore.

> [!NOTE]
> Gli aggiornamenti software per Microsoft Teams Rooms vengono scaricati automaticamente dal Microsoft Store per le aziende. Vedere [Prerequisiti per Microsoft Store per le aziende e Education](/microsoft-store/prerequisites-microsoft-store-for-business) per verificare che la console della sala sia in grado di accedere al negozio e di eseguire l'aggiornamento automatico.  

### <a name="selecting-a-language"></a>Selezione di una lingua 

In Creator's Update, è necessario usare lo script ApplyCurrentRegionAndLanguage.ps1 in scenari in cui la selezione implicita della lingua non fornisce all'utente la lingua effettiva dell'applicazione desiderata(ad esempio, vuole che l'app console sia disponibile in francese, ma sarà disponibile in inglese).
  
> [!NOTE]
> Le istruzioni seguenti funzionano solo per le console create Windows'aggiornamento di Creator.The following instructions work only for consoles created using Windows Creator's Update. I sistemi legacy/in-market che non sono stati impostati usando i supporti multimediali con il nuovo sistema di provisioning non potranno usare queste istruzioni, ma non dovranno risentire del problema iniziale che richiede questo intervento manuale (Anniversary Edition consente di scegliere esplicitamente la lingua dell'app nell'ambito della configurazione).
  
### <a name="to-apply-your-desired-language"></a>Per applicare la lingua desiderata

1. Passare alla modalità di amministrazione.
    
2. Selezionare il menu Start.
    
3. Seleziona l'icona a forma di ingranaggio per **avviare l Impostazioni app.**
    
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
    
La lingua desiderata viene ora applicata alla Microsoft Teams Rooms console.
## <a name="initial-set-up-of-the-console"></a>Configurazione iniziale della console
<a name="Initial"> </a>

Dopo Windows, l'app console di Microsoft Teams Rooms verrà avviata nel processo di installazione iniziale all'avvio successivo o se è stata scelta l'opzione /reboot.
  
1. Viene visualizzata la schermata Account utente. Immettere l Skype di accesso (in user@domain) dell'account della chat room da usare con la console.
    
2. Immettere la password per l'account della chat room e immetterla di nuovo per verificarla.
    
3. In "Configura dominio", impostare l'FQDN per il Skype for Business Server. Se il Skype for Business SIP è diverso dal dominio Exchange dell'utente, immettere il Exchange dominio in questo campo.
    
4. Fare clic su **Avanti**.
    
5. Selezionare i dispositivi indicati nella schermata Caratteristiche e fare clic su **Avanti.** Per impostazione predefinita, la condivisione automatica dello schermo è impostata su Su e Nascondi nomi riunione su Disattivato. I dispositivi da selezionare sono:
    
   - Microfono per conferenze: il microfono predefinito per questa sala riunioni.
    
   - Altoparlante per conferenza: l'altoparlante predefinito per le conferenze. 
    
   - Altoparlante predefinito: l'altoparlante usato per l'audio dall'ingestione HDMI.
    
     Ogni elemento ha un menu a discesa di opzioni tra cui selezionare. È necessario effettuare una selezione per ogni dispositivo.
    
6. Fare clic **su Fine.**
    
L Microsoft Teams Rooms app console di Skype for Business Server dovrebbe iniziare immediatamente ad accedere a Skype for Business Server con le credenziali immesse sopra e dovrebbe anche iniziare a sincronizzare il calendario con Exchange usando le stesse credenziali. Per informazioni dettagliate sull'uso dell'app console, vedere Microsoft Teams Rooms [guida.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)
  
> [!IMPORTANT]
> Microsoft Teams Rooms si basa sulla presenza di hardware della console certificato. Anche un'immagine creata correttamente contenente l Microsoft Teams Rooms app console non verrà avviato oltre la procedura di configurazione iniziale, a meno che non venga rilevato l'hardware della console. Per Surface Pro basate su dispositivi, il Surface Pro deve essere collegato all'hardware del dock di accompagnamento per superare questo controllo.
  
> [!NOTE]
> Alcuni utenti di lingue non inglesi potrebbero aver bisogno di una tastiera fisica connessa alla console durante la configurazione iniziale nel caso in cui i simboli non siano supportati sulla tastiera virtuale.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installare un certificato CA privato nella console
<a name="Certs"> </a>

La Microsoft Teams Rooms deve considerare attendibili i certificati usati dai server a cui si connette. Per O365 questa operazione viene eseguita automaticamente, perché questi server usano autorità di certificazione pubbliche e vengono automaticamente considerati attendibili da Windows 10. In un caso in cui l'Autorità di certificazione sia privata, ad esempio una distribuzione locale con Active Directory e l'Autorità di certificazione di Windows, è possibile aggiungere il certificato alla console di Microsoft Teams Rooms in un paio di modi:
  
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

È possibile aggiungere Microsoft Teams Rooms console al dominio. Microsoft Teams Rooms console devono essere inserite in un'unità organizzativa separata dalle workstation del PC, perché molti criteri workstation non sono compatibili con Microsoft Teams Rooms. Un esempio comune sono i criteri di applicazione delle password che impediscono Microsoft Teams Rooms l'avvio automatico. Per informazioni sulla gestione delle impostazioni degli oggetti Criteri di gruppo, vedere Gestire [Microsoft Teams Rooms](rooms-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Per aggiungere Microsoft Teams Rooms a un dominio

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
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft Teams Rooms di distribuzione
<a name="Checklist"> </a>

Usare l'elenco di controllo seguente durante una verifica finale che la console e tutte le relative periferiche siano completamente configurate:
  
**Impostazioni dell'applicazione**

|||
|:-----|:-----|
|☐  <br/> |Il nome dell'account della sala e il numero di telefono (se PSTN abilitato) vengono visualizzati correttamente nell'angolo in alto a destra dello schermo della console  <br/> |
|☐  <br/> |Windows il nome del computer è impostato correttamente (utile per l'amministrazione remota)  <br/> |
|☐  <br/> |Password dell'account amministratore impostata e verificata  <br/> |
|☐  <br/> |Tutti gli aggiornamenti del firmware sono stati applicati  <br/> |
   
**Periferiche audio/video**

|||
|:-----|:-----|
|☐  <br/> |La versione del firmware delle periferiche della fotocamera è corretta (se applicabile)  <br/> |
|☐  <br/> |Fotocamera funzionale e posizionata in modo ottimale  <br/> |
|☐  <br/> |Impostazioni dispositivo predefinito di riproduzione e dispositivo di comunicazione predefinito di riproduzione impostato sulla periferica audio prevista  <br/> |
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