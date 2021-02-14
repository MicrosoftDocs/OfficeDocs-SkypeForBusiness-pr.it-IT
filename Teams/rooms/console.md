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
description: Questo articolo descrive come configurare la console di Microsoft Teams Rooms e le sue periferiche.
ms.openlocfilehash: 7a36ed93f370c0aeb302da246b223732383719fb
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662061"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Configurare una console per Microsoft Teams Rooms

Questo articolo descrive come configurare la console di Microsoft Teams Room e le relative periferiche.
  
È consigliabile eseguire questi passaggi solo se gli account necessari di Microsoft Teams o Skype for Business ed Exchange sono già stati creati e testati come descritto in Distribuire sale [di Microsoft Teams.](rooms-deploy.md) Sono necessari l'hardware e il software descritti nei requisiti di [Microsoft Teams Room.](requirements.md) Questo argomento contiene le sezioni seguenti:
  
- [Preparare il supporto di installazione](console.md#Prep_Media)
- [Installare un certificato CA privato nella console](console.md#Certs)
- [Installare Windows 10 e l'app console Microsoft Teams Rooms](console.md#Reimage)
- [Configurazione iniziale della console](console.md#Initial)
- [Elenco di controllo per la distribuzione di Microsoft Teams Rooms](console.md#Checklist)

> [!NOTE]
> Le sale di Microsoft Teams funzionano solo in un ambiente Microsoft Teams o Skype for Business correttamente configurato in cui gli account del dispositivo sono configurati correttamente, come descritto in Distribuire sale [di Microsoft Teams.](rooms-deploy.md)
  
## <a name="prepare-the-installation-media"></a>Preparare il supporto di installazione
<a name="Prep_Media"> </a>

L'installazione dell'app console Microsoft Teams Rooms richiede un dispositivo di archiviazione USB con almeno 32 GB di capacità. Non dovrebbero esserci altri file nel dispositivo; eventuali file esistenti nell'archivio USB andranno persi.
  
> [!NOTE]
> Se non si crea il supporto di installazione delle sale di Microsoft Teams in base a queste istruzioni, è probabile che si crei un comportamento imprevisto.

> [!NOTE]
> La procedura seguente consente di creare un supporto di installazione per l'immagine di nuovi dispositivi di Microsoft Teams Room. Per impostazione predefinita, i dispositivi esistenti vengono aggiornati automaticamente da Windows Update e Windows Store.

> [!IMPORTANT]
> Il computer Windows 10 usato per creare il supporto di installazione Sale di Microsoft Teams deve essere nella stessa versione o versione successiva di Windows come supporto di installazione di destinazione.
  
1. Scaricare lo [scriptCreateSrsMedia.ps1.](https://go.microsoft.com/fwlink/?linkid=867842)
2. Eseguire lo script CreateSrsMedia.ps1 da un prompt con privilegi elevati in un computer Windows 10.
3. Seguire le istruzioni dello script per creare un disco di configurazione USB di Microsoft Teams Rooms.


> [!TIP]
> Ogni volta che CreateSrsMedia.ps1 script personalizzato, l'output dello schermo includerà il nome di un file di log o la trascrizione per la sessione. Se ci sono problemi con l'esecuzione dello script, assicurarsi di avere una copia di quella trascrizione disponibile quando si richiede supporto. 

Lo CreateSrsMedia.ps1 script automatizza le attività seguenti:

1. Scaricare il programma di installazione MSI più recente per Microsoft Teams Rooms.
2. Determinare la build di Windows che l'utente deve fornire. Le versioni più recenti possono essere testate e supportate per l'uso con i dispositivi Microsoft Teams Rooms.
3. Scaricare i componenti di supporto necessari.
4. Assemblare i componenti necessari nel supporto di installazione.

È necessaria una versione specifica di Windows 10, che è disponibile solo per i clienti con contratti multilicenza.  È possibile ottenerne una copia dal [Centro servizi per contratti multilicenza.](https://www.microsoft.com/Licensing/servicecenter/)

Al termine, rimuovere il disco USB dal computer e procedere con l'installazione di [Windows 10 e dell'app console Microsoft Teams Rooms.](console.md#Reimage)

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installare Windows 10 e l'app console Microsoft Teams Rooms
<a name="Reimage"> </a>

A questo punto è necessario applicare il supporto di configurazione creato. Il dispositivo di destinazione verrà eseguito come appliance e l'utente predefinito verrà impostato in modo da eseguire solo l'app console Microsoft Teams Rooms.

1. Se il dispositivo di destinazione verrà installato in un dock (ad esempio Surface Pro), scollegarlo dal dock.

2. Verificare che il dispositivo di destinazione non sia connesso alla rete.

3. Verificare che il dispositivo di destinazione sia connesso all'alimentazione CA.

4. Collega il disco di configurazione USB al dispositivo di destinazione.

5. Eseguire l'avvio nel disco di configurazione USB. Consulta le istruzioni del produttore. Se il dispositivo di destinazione è un Surface Pro, usare la procedura seguente per avviare il disco di configurazione USB:

    a. Tieni premuto e continua a tenere premuto il pulsante per il volume (-).

    b. Premere e rilasciare il pulsante di alimentazione.

    c. Dopo l'avvio dell'installazione di Windows, rilasciare il pulsante di basso volume (-).

8. Il sistema verrà arrestato al termine dell'installazione.
    
Dopo l'arresto del sistema, è possibile rimuovere il disco di configurazione USB. A questo punto, è possibile inserire il dispositivo di destinazione nella dock (se si utilizza un prodotto basato su dock), collegare le periferiche necessarie per la sala riunioni e connettersi alla rete. Consulta le istruzioni del produttore.

> [!NOTE]
> Gli aggiornamenti software per le sale di Microsoft Teams vengono scaricati automaticamente da Microsoft Store per le aziende. Vedi [i prerequisiti di Microsoft Store per le aziende](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) e la formazione per verificare che la console della sala possa accedere al negozio e eseguire l'aggiornamento in autonomia.  

### <a name="selecting-a-language"></a>Selezione di una lingua 

In Creator's Update è necessario usare lo script ApplyCurrentRegionAndLanguage.ps1 in scenari in cui la selezione implicita del linguaggio non fornisce all'utente il linguaggio effettivo dell'applicazione desiderato (ad esempio, vuole che l'app console sia disponibile in francese, ma verrà presto disponibile in inglese).
  
> [!NOTE]
> Le istruzioni seguenti funzionano solo per le console create con Windows Creator's Update. I sistemi legacy/in-market che non sono stati impostati usando elementi multimediali con il nuovo sistema di provisioning non saranno in grado di usare queste istruzioni, ma non dovrebbero risentire del problema iniziale che richiede questo intervento manuale (Anniversary Edition consente di selezionare esplicitamente la lingua dell'app durante la configurazione).
  
### <a name="to-apply-your-desired-language"></a>Per applicare la lingua desiderata

1. Passare alla modalità amministratore.
    
2. Selezionare il menu Start.
    
3. Selezionare l'icona a forma di ingranaggio per avviare **l'app** Impostazioni.
    
4. Selezionare **Lingua &amp; ora.**
    
5. Selezionare **la lingua &amp; dell'area geografica.**
    
6. Selezionare **Aggiungi una lingua.**
    
7. Seleziona la lingua che desideri aggiungere.
    
8. Selezionare la lingua appena aggiunta all'elenco "Lingue".
    
9. Selezionare **Imposta come predefinito.**
    
10. Per tutte le lingue che si desidera rimuovere:
    
    a. Seleziona la lingua che desideri rimuovere.
    
    b. Selezionare **Rimuovi.**
    
11. Avviare un prompt dei comandi con privilegi elevati.
    
12. Eseguire il comando seguente: 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. Riavviare il sistema.
    
La lingua desiderata è ora applicata alla console di Microsoft Teams Rooms.
## <a name="initial-set-up-of-the-console"></a>Configurazione iniziale della console
<a name="Initial"> </a>

Dopo l'installazione di Windows, l'app console Microsoft Teams Rooms entra nel processo di configurazione iniziale al successivo avvio o se è stata scelta l'opzione /reboot.
  
1. Viene visualizzata la schermata Account utente. Immetti l'indirizzo di accesso Skype (in user@domain) dell'account della sala da utilizzare con la console.
    
2. Immettere la password dell'account della chat room e quindi immetterla di nuovo per verificarla.
    
3. In "Configurazione dominio" impostare l'FQDN per Skype for Business Server. Se il dominio SIP di Skype for Business è diverso dal dominio Exchange dell'utente, immettere il dominio di Exchange in questo campo.
    
4. Fare clic su **Avanti**.
    
5. Selezionare i dispositivi indicati nella schermata Funzionalità e fare clic su **Avanti.** Per impostazione predefinita, la condivisione automatica dello schermo è impostata su On e l'opzione Nascondi nomi riunione è disattivata. I dispositivi da selezionare sono:
    
   - Microfono per le conferenze: microfono predefinito per questa sala riunioni.
    
   - Altoparlante per le conferenze: l'altoparlante predefinito per le conferenze. 
    
   - Altoparlante predefinito: l'altoparlante utilizzato per l'audio da HDMI ingestito.
    
     Ogni voce ha un menu a discesa con le opzioni tra cui selezionare. È necessario effettuare una selezione per ogni dispositivo.
    
6. Fare clic **su Fine.**
    
L'app console Microsoft Teams Rooms dovrebbe iniziare immediatamente ad accedere a Skype for Business Server con le credenziali immesse sopra e dovrebbe anche iniziare a sincronizzare il calendario con Exchange con le stesse credenziali. Per i dettagli sull'uso dell'app console, consulta la Guida di [Microsoft Teams Rooms.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)
  
> [!IMPORTANT]
> Microsoft Teams Rooms si basa sulla presenza di hardware della console certificato. Anche un'immagine creata correttamente contenente l'app della console Microsoft Teams Rooms non verrà avviato dopo la procedura di configurazione iniziale, a meno che non venga rilevato l'hardware della console. Per le soluzioni basate su Surface Pro, Surface Pro deve essere collegato al relativo hardware dock di accompagnamento per superare questo controllo.
  
> [!NOTE]
> Alcuni utenti di lingue non inglesi potrebbero avere bisogno di una tastiera fisica connessa alla console durante la configurazione iniziale, nel caso in cui i simboli non siano supportati sulla tastiera virtuale.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installare un certificato CA privato nella console
<a name="Certs"> </a>

La console Microsoft Teams Rooms deve considerare attendibili i certificati usati dai server a cui si connette. Per O365 questa operazione viene eseguita automaticamente, perché questi server usano autorità di certificazione pubbliche e questi vengono automaticamente considerati attendibili da Windows 10. In un caso in cui l'Autorità di certificazione sia privata, ad esempio una distribuzione locale con Active Directory e l'Autorità di certificazione di Windows, è possibile aggiungere il certificato alla console Sale di Microsoft Teams in due modi:
  
- È possibile aggiungere la console ad Active Directory, che aggiungerà automaticamente i certificati necessari, dato che l'Autorità di certificazione è pubblicata in Active Directory (normale opzione di distribuzione).
    
- È possibile installare manualmente il certificato dopo il processo di creazione dell'immagine. Prima di eseguire questa operazione, è necessario [completare la configurazione iniziale della console.](console.md#Initial)
    
### <a name="to-manually-install-the-certificate"></a>Per installare manualmente il certificato

1. Scaricare il certificato CA nel computer e salvarlo in "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Attiva la modalità amministratore per la console (vedi [la modalità di amministrazione e la gestione dei dispositivi).](rooms-operations.md#AdminMode)
    
3. Eseguire il comando seguente:
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Aggiunta a un dominio Active Directory (facoltativo)
<a name="Certs"> </a>

È possibile aggiungere le console di Microsoft Teams Rooms al proprio dominio. Le console di Microsoft Teams Rooms devono essere collocate in un'unità organizzativa separata dalle workstation del PC in quanto molti criteri della workstation non sono compatibili con le sale di Microsoft Teams. Un esempio comune sono i criteri di applicazione delle password che impediscono l'avvio automatico di Sale di Microsoft Teams. Per informazioni sulla gestione delle impostazioni dell'oggetto Criteri di gruppo, vedere [Gestire le sale di Microsoft Teams.](rooms-operations.md)
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Per aggiungere sale di Microsoft Teams a un dominio

1. Accedi alla console dall'account amministratore (vedi [modalità amministratore e gestione dei dispositivi).](rooms-operations.md#AdminMode)
    
2. Avviare un prompt dei comandi di PowerShell con privilegi elevati.
    
3. Immettere il comando seguente in Powershell:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Ad esempio, se il dominio completo è redmond.corp.microsoft.com e si vuole che le console di Microsoft Teams Room si abilitino in un'unità organizzativa "Sale di Microsoft Teams" figlio di un'unità organizzativa "Risorse", il comando sarà:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Se si vuole rinominare il computer quando lo si unisce a un dominio, usare il contrassegno -NewName seguito dal nuovo nome del computer.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Elenco di controllo per la distribuzione di Microsoft Teams Rooms
<a name="Checklist"> </a>

Usare l'elenco di controllo seguente durante una verifica finale che conferma che la console e tutte le relative periferiche sono completamente configurate:
  
**Impostazioni applicazione**

|||
|:-----|:-----|
|☐  <br/> |Il nome dell'account della sala e il numero di telefono (se PSTN abilitato) vengono visualizzati correttamente nell'angolo in alto a destra dello schermo della console  <br/> |
|☐  <br/> |Il nome del computer Windows è impostato correttamente (utile per l'amministrazione remota)  <br/> |
|☐  <br/> |Password dell'account amministratore impostata e verificata  <br/> |
|☐  <br/> |Tutti gli aggiornamenti del firmware sono stati applicati  <br/> |
   
**Periferiche audio/video**

|||
|:-----|:-----|
|☐  <br/> |La versione del firmware della videocamera è corretta (se applicabile)  <br/> |
|☐  <br/> |Fotocamera funzionale e posizionata in modo ottimale  <br/> |
|☐  <br/> |Impostazioni del dispositivo di riproduzione predefinito per la riproduzione e del dispositivo di comunicazione predefinito per la riproduzione impostato sulla periferia audio prevista  <br/> |
|☐  <br/> |Impostazioni per la registrazione del dispositivo di comunicazione predefinito impostato sulla periferia audio prevista  <br/> |
|☐  <br/> |La versione del firmware delle periferiche audio è corretta (se applicabile)  <br/> |
|☐  <br/> |Dispositivo di input audio con funzionamento e posizionamento ottimale  <br/> |
|☐  <br/> |Dispositivo di output audio funzionale e con posizionamento ottimale  <br/> |
   
**Dock**

|||
|:-----|:-----|
|☐  <br/> |I cavi sono protetti e non avvicinati  <br/> |
|☐  <br/> |L'audio ingestito su HDMI funziona  <br/> |
|☐  <br/> |Il video ingestito su HDMI funziona  <br/> |
|☐  <br/> |Dock può ruotare liberamente  <br/> |
|☐  <br/> |La luminosità dello schermo è accettabile per l'ambiente  <br/> |
   
## <a name="see-also"></a>Vedere anche
<a name="Checklist"> </a>

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
