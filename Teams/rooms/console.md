---
title: Creare un'Microsoft Teams Rooms immagine
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Questo articolo descrive come configurare la console di Microsoft Teams Rooms e le relative periferiche.
ms.openlocfilehash: d6c675ed6eb6f50cf41b817770caf723f75f556b
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055646"
---
# <a name="build-a-microsoft-teams-rooms-image"></a>Creare un'Microsoft Teams Rooms immagine

Questo articolo descrive come creare un'immagine Microsoft Teams Rooms per la distribuzione di massa di Teams Rooms.

> [!NOTE]
> I passaggi seguenti devono essere usati solo quando si crea [un'immagine basata su WIM](/windows-hardware/manufacture/desktop/capture-and-apply-an-image) per la distribuzione di massa. Se si recuperano singoli dispositivi, contattare l'OEM (Original Equipment Manufacturer) per assistenza.

È consigliabile eseguire questa procedura solo se gli account Microsoft Teams o Skype for Business e Exchange sono già stati creati e testati come descritto in [Distribuire Microsoft Teams Rooms](rooms-deploy.md). Sono necessari l'hardware e il software descritti in Microsoft Teams Rooms [requisiti.](requirements.md) Questo argomento contiene le sezioni seguenti:
  
- [Preparare il supporto di installazione](console.md#Prep_Media)
- [Installare un certificato CA privato nella console](console.md#Certs)
- [Installare Windows 10 e l'app Microsoft Teams Rooms console](console.md#Reimage)
- [Configurazione iniziale della console](console.md#Initial)
- [Microsoft Teams Rooms di distribuzione](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>Preparare il supporto di installazione
<a name="Prep_Media"> </a>

L'installazione dell Microsoft Teams Rooms app console richiede un dispositivo di archiviazione USB con almeno 32 GB di capacità. Nel dispositivo non dovrebbero essere presenti altri file. i file esistenti sullo spazio di archiviazione USB andranno persi.
  
> [!NOTE]
> Se non si crea il Microsoft Teams Rooms di installazione in base a queste istruzioni, è probabile che si crei un comportamento imprevisto.

> [!NOTE]
> Il processo seguente consente di creare supporti di installazione per immagini di Microsoft Teams Rooms dispositivi. I dispositivi esistenti, per impostazione predefinita, vengono aggiornati automaticamente Windows Update e Windows Store.

> [!IMPORTANT]
> Il Windows 10 usato per creare il supporto di Microsoft Teams Rooms di installazione deve essere nella stessa o versione successiva di Windows come supporto di installazione di destinazione.
  
1. Scaricare lo [scriptCreateSrsMedia.ps1 .](https://go.microsoft.com/fwlink/?linkid=867842)
2. Eseguire lo script CreateSrsMedia.ps1 da un prompt con privilegi elevati in un Windows 10 computer.
3. Seguire le istruzioni dello script per creare un disco di Microsoft Teams Rooms usb.


> [!TIP]
> Ogni volta che lo script CreateSrsMedia.ps1, l'output dello schermo includerà il nome di un file di log o di una trascrizione per la sessione. In caso di problemi con l'esecuzione dello script, assicurarsi di avere una copia della trascrizione disponibile quando si richiede il supporto. 

Lo script CreateSrsMedia.ps1 automatizza le attività seguenti:

1. Scaricare il programma di installazione MSI più recente per Microsoft Teams Rooms.
2. Determinare la build di Windows che l'utente deve fornire. Le versioni rilasciate più di recente possono essere testate e supportate per l'uso con Microsoft Teams Rooms dispositivi.
3. Scaricare i componenti di supporto necessari.
4. Assemblare i componenti necessari sul supporto di installazione.

> [!NOTE]
È necessaria una versione specifica Windows 10 e questa versione è disponibile solo per i clienti con contratto multilicenza.  È possibile ottenere una copia dal [Centro servizi per contratti multilicenza.](https://www.microsoft.com/Licensing/servicecenter/)

Al termine, rimuovere il disco USB dal computer e passare a Installa [Windows 10 e all'app Microsoft Teams Rooms console.](console.md#Reimage)

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installare Windows 10 e l'app Microsoft Teams Rooms console
<a name="Reimage"> </a>

A questo punto è necessario applicare il supporto di configurazione creato. Il dispositivo di destinazione verrà eseguito come appliance e l'utente predefinito sarà impostato in modo da eseguire solo l'app Microsoft Teams Rooms predefinita.

1. Se il dispositivo di destinazione verrà installato in un dock (ad esempio un Surface Pro), scollegarlo dal dock.

2. Verificare che il dispositivo di destinazione non sia connesso alla rete.

3. Verificare che il dispositivo di destinazione sia connesso all'alimentazione CA.

4. Collegare il disco di configurazione USB al dispositivo di destinazione.

5. Eseguire l'avvio sul disco di configurazione USB. Fare riferimento alle istruzioni del produttore. Se il dispositivo di destinazione è Surface Pro, eseguire la procedura seguente per eseguire l'avvio sul disco di configurazione USB:

    a. Premere e continuare a tenere premuto il pulsante del volume (-).

    b. Premere e rilasciare il pulsante di alimentazione.

    c. Dopo Windows l'avvio dell'installazione, rilasciare il pulsante volume verso il basso (-).

8. Il sistema verrà arrestato al termine dell'installazione.
    
Dopo l'arresto del sistema, è possibile rimuovere il disco di configurazione USB. A questo punto, è possibile posizionare il dispositivo di destinazione nel dock (se si usa un prodotto basato su dock), collegare le periferiche necessarie per la sala riunioni e connettersi alla rete. Fare riferimento alle istruzioni del produttore.

> [!NOTE]
> Gli aggiornamenti software per Microsoft Teams Rooms vengono scaricati automaticamente dal Microsoft Store per le aziende. Vedere [Prerequisiti per Microsoft Store per le aziende e Education](/microsoft-store/prerequisites-microsoft-store-for-business) per verificare che la console della sala sia in grado di accedere al negozio e di eseguire l'aggiornamento automatico.  

### <a name="selecting-a-language"></a>Selezione di una lingua 

In Creator's Update, è necessario usare lo script ApplyCurrentRegionAndLanguage.ps1 in scenari in cui la selezione implicita della lingua non fornisce all'utente la lingua effettiva dell'applicazione desiderata (ad esempio, vuole che l'app console sia disponibile in francese, ma verrà disponibile in inglese).
  
> [!NOTE]
> Le istruzioni seguenti funzionano solo per le console create con Windows Creator's Update (Windows 10 20H1) o versioni successive.
  
### <a name="to-apply-your-desired-language"></a>Per applicare la lingua desiderata

1. Passare alla modalità di amministrazione.
    
2. Selezionare la menu Start.
    
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

Dopo Windows, l'app Microsoft Teams Rooms verrà installata nel processo di configurazione iniziale.
  
1. Viene visualizzata la schermata Account utente. Immettere l'indirizzo di accesso dell'account microsoft Exchange risorsa (nel formato user@domain) dell'account della chat room da usare con la console.
    
2. Immettere la password per l'account della chat room e immetterla di nuovo per verificarla.
   
3. Selezionare la modalità riunione supportata: solo Microsoft Teams, Skype for Business solo o una delle due opzioni in modalità mista. Se necessario, abilitare l'autenticazione moderna.

4. Fare clic su **Avanti**.
    
5. Se si usa Skype for Business e se il dominio SIP di Skype for Business è diverso dal dominio Exchange dell'utente, impostare l'FQDN per il Skype for Business Server nella sezione Avanzate. Se non si usa un Skype for Business o se il dominio SIP corrisponde al dominio Exchange, lasciare vuota questa sezione.
6. Fare clic su **Avanti**.
    
7. Fare clic **su Fine.**
    
L'app Microsoft Teams Rooms deve accedere a Microsoft Teams o Skype for Business Server con le credenziali immesse in precedenza e deve anche iniziare a sincronizzare il calendario con Exchange usando le stesse credenziali. Per informazioni dettagliate sull'Teams Rooms, vedere la [Guida Microsoft Teams Rooms guida.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)
  
> [!IMPORTANT]
> Microsoft Teams Rooms si basa sulla presenza di hardware della console certificato. Anche un'immagine creata correttamente contenente l'app console Microsoft Teams Rooms non verrà avviato oltre la procedura di configurazione iniziale, a meno che non venga rilevato l'hardware della console. Per Surface Pro, il Surface Pro deve essere collegato all'hardware del dock di accompagnamento per superare questo controllo.
  
> [!NOTE]
> Alcuni utenti di lingue non inglesi potrebbero aver bisogno di una tastiera fisica connessa alla console durante la configurazione iniziale nel caso in cui i simboli non siano supportati sulla tastiera virtuale.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installare un certificato CA privato nella console
<a name="Certs"> </a>
> [!NOTE]
> Quanto segue si applica solo se ci si connette Teams Rooms a Skype for Business.

Microsoft Teams Rooms deve considerare attendibili i certificati usati dai server a cui si connette. In un caso in cui l'Autorità di certificazione sia privata, ad esempio una distribuzione locale con Active Directory e l'Autorità di certificazione di Windows, è possibile aggiungere il certificato a Microsoft Teams Rooms in un paio di modi:
  
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

È possibile aggiungere Microsoft Teams Rooms al dominio. Microsoft Teams Rooms devono essere inseriti in un'unità organizzativa separata dalle workstation del PC perché molti criteri di workstation non sono compatibili con Microsoft Teams Rooms. Un esempio comune sono i criteri di imposizione delle password che impediscono Microsoft Teams Rooms l'avvio automatico. Per informazioni sulla gestione delle impostazioni dell'oggetto Criteri di gruppo, vedere [Gestire Microsoft Teams Rooms](rooms-operations.md).
  
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

|Completato |Verifica |
|:-----:|:-----|
|☐   |Il nome dell'account della sala e il numero di telefono (se PSTN abilitato) vengono visualizzati correttamente   |
|☐   |Windows il nome del computer è impostato correttamente (utile per l'amministrazione remota)   |
|☐   |Password dell'account amministratore impostata e verificata   |
|☐   |Tutti gli aggiornamenti del firmware sono stati applicati   |
   
**Periferiche audio/video**

|Completato |Verifica |
|:-----:|:-----|
|☐   |La versione del firmware delle periferiche della fotocamera è corretta (se applicabile)   |
|☐   |Fotocamera funzionale e posizionata in modo ottimale   |
|☐   |Impostazioni per Dispositivo predefinito di riproduzione e Dispositivo di comunicazione predefinito riproduzione impostato sulla periferica audio prevista   |
|☐   |Impostazioni per Registrazione dispositivo di comunicazione predefinito impostato sulla periferica audio prevista   |
|☐   |La versione del firmware delle periferiche audio è corretta (se applicabile)   |
|☐   |Dispositivo di input audio funzionale e posizionato in modo ottimale   |
|☐   |Dispositivo di output audio funzionante e posizionato in modo ottimale   |

**Console**

|Completato |Verifica |
|:-----:|:-----|
|☐   |I cavi sono sicuri e non pizzicati   |
|☐   |L'inserimento audio tramite HDMI è funzionale   |
|☐   |L'inserimento di video su HDMI è funzionale   |
|☐   |La console può ruotare liberamente   |



   
## <a name="see-also"></a>Vedere anche
<a name="Checklist"> </a>

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
