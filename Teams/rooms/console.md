---
title: Creare un'immagine Microsoft Teams Rooms
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
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Questo articolo descrive come configurare la console Microsoft Teams Rooms e le relative periferiche.
ms.openlocfilehash: 40d49597ab3354eeaacc8d7c562917fbf653e727
ms.sourcegitcommit: 9a9168d5c40bbb0cceaf3ffd11eb104c137f26b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2022
ms.locfileid: "67590173"
---
# <a name="build-a-microsoft-teams-rooms-image"></a>Creare un'immagine Microsoft Teams Rooms

Questo articolo descrive come creare un'immagine Microsoft Teams Rooms per la distribuzione di massa di Teams Rooms.

> [!NOTE]
> I passaggi seguenti devono essere usati solo quando si crea [un'immagine basata su WIM](/windows-hardware/manufacture/desktop/capture-and-apply-an-image) per la distribuzione di massa. Se stai recuperando singoli dispositivi, contatta l'OEM (Original Equipment Manufacturer) per ricevere supporto.

È consigliabile eseguire questi passaggi solo se gli account di Microsoft Teams o Skype for Business ed Exchange necessari sono già stati creati e testati, come descritto in [Distribuire Microsoft Teams Rooms](rooms-deploy.md). Saranno necessari l'hardware e il software descritti in [Microsoft Teams Rooms requisiti](requirements.md). Questo argomento contiene le sezioni seguenti:
  
- [Preparare il supporto di installazione](console.md#Prep_Media)
- [Installare un certificato CA privato nella console](console.md#Certs)
- [Installare Windows 10 e l'app della console Microsoft Teams Rooms](console.md#Reimage)
- [Configurazione iniziale della console](console.md#Initial)
- [elenco di controllo per la distribuzione di Microsoft Teams Rooms](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>Preparare il supporto di installazione
<a name="Prep_Media"> </a>

L'installazione dell'app console Microsoft Teams Rooms richiede un dispositivo di archiviazione USB con almeno 32 GB di capacità. Non dovrebbero esserci altri file nel dispositivo; eventuali file presenti nella memoria USB andranno persi.
  
> [!NOTE]
> Se non si crea il supporto di installazione di Microsoft Teams Rooms in base a queste istruzioni, è probabile che si verifichi un comportamento imprevisto.

> [!NOTE]
> La procedura seguente consente di creare il supporto di installazione per l'immagine di nuovi dispositivi Microsoft Teams Rooms. Per impostazione predefinita, i dispositivi esistenti vengono aggiornati automaticamente da Windows Update e Da Windows Store.

> [!IMPORTANT]
> Il computer Windows 10 usato per creare il supporto di installazione Microsoft Teams Rooms deve trovarsi nella stessa versione o versione successiva di Windows del supporto di installazione di destinazione.
  
1. Scaricare lo [ scriptCreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).
2. Eseguire lo script CreateSrsMedia.ps1 da un prompt con privilegi elevati in un computer Windows 10.
3. Segui le istruzioni dello script per creare un Microsoft Teams Rooms disco di installazione USB.


> [!TIP]
> Ogni volta che viene avviato lo script CreateSrsMedia.ps1, l'output dello schermo includerà il nome di un file di log o una trascrizione per la sessione. Se si verificano problemi con l'esecuzione dello script, assicurarsi di avere una copia della trascrizione disponibile quando si richiede supporto. 

Lo script CreateSrsMedia.ps1 automatizza le attività seguenti:

1. Scarica il programma di installazione MSI più recente per Microsoft Teams Rooms.
2. Determinare la build di Windows che l'utente deve fornire. È possibile che le versioni più recenti rilasciate siano o meno testate e supportate per l'uso con dispositivi Microsoft Teams Rooms.
3. Scarica i componenti di supporto necessari.
4. Assemblare i componenti necessari sul supporto di installazione.

> [!NOTE]
È necessaria una versione specifica di Windows 10 e questa versione è disponibile solo per i clienti con contratti multilicenza.  È possibile otrne una copia dal [Centro servizi per contratti multilicenza](https://www.microsoft.com/Licensing/servicecenter/).

Al termine, rimuovere il disco USB dal computer e procedere con [Installa Windows 10 e l'app console Microsoft Teams Rooms](console.md#Reimage).

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installare Windows 10 e l'app della console Microsoft Teams Rooms
<a name="Reimage"> </a>

Ora è necessario applicare il supporto di configurazione creato. Il dispositivo di destinazione verrà eseguito come accessorio e l'utente predefinito sarà impostato per eseguire solo l'app Microsoft Teams Rooms.

1. Se il dispositivo di destinazione verrà installato in un dock (ad esempio, un Surface Pro), scollegalo dal dock.

2. Assicurati che il dispositivo di destinazione non sia connesso alla rete.

3. Assicurati che il dispositivo di destinazione sia connesso all'alimentazione CA.

4. Collega il disco di installazione USB al dispositivo di destinazione.

5. Esegui l'avvio sul disco di installazione USB. Fai riferimento alle istruzioni del produttore. Se il dispositivo di destinazione è un Surface Pro, utilizza i passaggi seguenti per avviare il disco di installazione USB:

    a. Tieni premuto il pulsante di riduzione del volume (-).

    b. Premi e rilascia il pulsante di alimentazione.

    C. Dopo aver avviato l'installazione di Windows, rilascia il pulsante di riduzione del volume (-).

8. Il sistema verrà arrestato al termine dell'installazione.
    
Dopo l'arresto del sistema, è possibile rimuovere il disco di installazione USB. A questo punto, è possibile inserire il dispositivo di destinazione nel dock (se si usa un prodotto basato su dock), collegare le periferiche necessarie per la sala riunioni e connettersi alla rete. Fai riferimento alle istruzioni del produttore.

> [!NOTE]
> Gli aggiornamenti software per Microsoft Teams Rooms vengono scaricati automaticamente dal Microsoft Store per le aziende. Vedi [Prerequisiti per Microsoft Store per le aziende ed Istruzione](/microsoft-store/prerequisites-microsoft-store-for-business) per verificare che la console della sala possa accedere allo Store e all'aggiornamento automatico.  

### <a name="selecting-a-language"></a>Selezione di una lingua 

In Creator's Update, dovrai usare lo script ApplyCurrentRegionAndLanguage.ps1 in scenari in cui la selezione implicita della lingua non fornisce all'utente la lingua effettiva dell'applicazione desiderata (ad esempio, vuole che l'app console venga visualizzata in francese, ma sta arrivando in inglese).
  
> [!NOTE]
> Le istruzioni seguenti funzionano solo per le console create con Windows Creator's Update (Windows 10 20H1) o versioni successive.
  
### <a name="to-apply-your-desired-language"></a>Per applicare la lingua desiderata

1. Passare alla modalità Amministrazione.
    
2. Seleziona il menu Start.
    
3. Seleziona l'icona dell'ingranaggio per avviare l'app **Impostazioni** .
    
4. Selezionare **Lingua ora&amp;**.
    
5. Selezionare la **lingua**.
    
6. Seleziona **Aggiungi una lingua**.
    
7. Seleziona la lingua che vuoi aggiungere.
    
8. Installare le funzionalità per la lingua.
    
9. Non selezionare Imposta come lingua di visualizzazione di Windows.
    
10. Seleziona **Installa**.
    
11. Selezionare la lingua appena aggiunta all'elenco "Lingue".
    
12. Imposta come predefinito- Sposta la freccia su per impostare l'impostazione predefinita

13. Per tutte le lingue da rimuovere:
    
    a. Seleziona la lingua che vuoi rimuovere.
    
    b. Seleziona Rimuovi.

14. Avviare un prompt dei comandi con privilegi elevati.

15. Eseguire il comando seguente: 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
16. Riavvia il sistema.
    
La lingua desiderata è ora applicata alla console Microsoft Teams Rooms.
## <a name="initial-set-up-of-the-console"></a>Configurazione iniziale della console
<a name="Initial"> </a>

Dopo l'installazione di Windows, l'app Microsoft Teams Rooms passerà al processo di installazione iniziale.
  
1. Viene visualizzata la schermata Account utente. Immettere l'indirizzo di accesso all'account di risorse di Microsoft Exchange (nel formato user@domain) dell'account della chat room da usare con la console.
    
2. Immettere la password dell'account della chat room e immetterla di nuovo per verificarla.
   
3. Selezionare la modalità riunione supportata - Solo Microsoft Teams, solo Skype for Business o una delle due opzioni in modalità mista. Se necessario, abilitare l'autenticazione moderna.

4. Selezionare **Avanti**.
    
5. Se si usa Skype for Business e se il dominio SIP Skype for Business è diverso dal dominio di Exchange dell'utente, impostare l'FQDN per il Skype for Business Server nella sezione Avanzate. Se non si usa Skype for Business o il dominio SIP corrisponde al dominio di Exchange, lasciare vuota questa sezione.
6. Selezionare **Avanti**.
    
7. Selezionare **Fine**.
    
L'app Microsoft Teams Rooms deve accedere a Microsoft Teams o Skype for Business Server con le credenziali immesse sopra e dovrebbe anche iniziare a sincronizzare il calendario con Exchange usando le stesse credenziali. Per informazioni dettagliate sull'uso di Teams Rooms, vedere la [Guida di Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Microsoft Teams Rooms si basa sulla presenza di hardware per console certificato. Anche un'immagine creata correttamente contenente l'app console Microsoft Teams Rooms non verrà avviata oltre la procedura di configurazione iniziale, a meno che non sia stato rilevato l'hardware della console. Per Surface Pro soluzioni basate, il Surface Pro deve essere collegato all'hardware del dock associato per superare questo controllo. Per altre informazioni sull'hardware supportato, vedere [requisiti di Microsoft Teams Rooms](requirements.md).
  
> [!NOTE]
> Alcuni utenti non in lingua inglese potrebbero aver bisogno di una tastiera fisica collegata alla console durante l'installazione iniziale nel caso in cui i simboli non siano supportati sulla tastiera virtuale.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installare un certificato CA privato nella console
<a name="Certs"> </a>
> [!NOTE]
> Quanto segue si applica solo se ci si connette Teams Rooms a Skype for Business.

Microsoft Teams Rooms deve considerare attendibili i certificati usati dai server a cui si connette. Se l'Autorità di certificazione è privata, ad esempio una distribuzione locale con Active Directory e l'Autorità di certificazione Windows, è possibile aggiungere il certificato a Microsoft Teams Rooms in due modi:
  
- È possibile unire la console ad Active Directory e che aggiungerà automaticamente i certificati necessari dato che l'autorità di certificazione è pubblicata in Active Directory (opzione di distribuzione normale).
    
- È possibile installare manualmente il certificato dopo il processo di creazione dell'immagine. Prima di eseguire questa operazione, è necessario completare [la configurazione iniziale della console](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>Per installare manualmente il certificato

1. Scarica il certificato CA nel computer e salvalo in "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Posiziona la console in modalità di amministrazione (vedi [modalità Amministrazione e gestione dei dispositivi](rooms-operations.md#AdminMode)).
    
3. Eseguire il comando seguente:
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Aggiungere un dominio Active Directory (facoltativo)
<a name="Certs"> </a>

È possibile aggiungere Microsoft Teams Rooms al proprio dominio. Microsoft Teams Rooms devono essere posizionate in un'unità organizzativa separata dalle workstation del PC perché molti criteri di workstation non sono compatibili con Microsoft Teams Rooms. Un esempio comune è costituito da criteri di applicazione delle password che impediscono l'avvio automatico di Microsoft Teams Rooms. Per informazioni sulla gestione delle impostazioni dell'oggetto Criteri di gruppo, vedere [Gestire Microsoft Teams Rooms](rooms-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Per aggiungere Microsoft Teams Rooms a un dominio

1. Accedi alla console dall'account amministratore (vedi [modalità Amministrazione e gestione dei dispositivi](rooms-operations.md#AdminMode)).
    
2. Avvia il prompt dei comandi con privilegi elevati di PowerShell.
    
3. Immettere il comando seguente in Powershell:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, ... ,OU=<Top level OU>,DC=<child domain>,...,DC=<top level domain>"
   ```

Ad esempio, se il dominio completo è redmond.corp.microsoft.com e si vuole che le console Microsoft Teams Rooms siano in un'unità organizzativa "Microsoft Teams Rooms" figlio di un'unità organizzativa "Resources", il comando sarà:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Se si vuole rinominare il computer quando lo si aggiunge a un dominio, usare il flag -NewName seguito dal nuovo nome del computer.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>elenco di controllo per la distribuzione di Microsoft Teams Rooms
<a name="Checklist"> </a>

Utilizza l'elenco di controllo seguente mentre esegui una verifica finale che la console e tutte le relative periferiche siano completamente configurate:
  
**Impostazioni delle applicazioni**

|Completato |Verifica |
|:-----:|:-----|
|☐   |Il nome dell'account della sala e il numero di telefono (se PSTN è abilitato) vengono visualizzati correttamente   |
|☐   |Il nome del computer Windows è impostato correttamente (utile per l'amministrazione remota)   |
|☐   |Password dell'account amministratore impostata e verificata   |
|☐   |Tutti gli aggiornamenti del firmware sono stati applicati   |
   
**Periferiche audio/video**

|Completato |Verifica |
|:-----:|:-----|
|☐   |La versione del firmware della periferica della fotocamera è corretta (se applicabile)   |
|☐   |Fotocamera funzionale e posizionata in modo ottimale   |
|☐   |Impostazioni per il dispositivo predefinito di riproduzione e il dispositivo di comunicazione predefinito per la riproduzione impostati sulla periferica audio prevista   |
|☐   |Impostazioni per la registrazione del dispositivo di comunicazione predefinito impostato sulla periferica audio prevista   |
|☐   |La versione del firmware della periferica audio è corretta (se applicabile)   |
|☐   |Dispositivo di input audio funzionale e posizionato in modo ottimale   |
|☐   |Dispositivo di output audio funzionale e posizionato in modo ottimale   |

**Console**

|Completato |Verifica |
|:-----:|:-----|
|☐   |I cavi sono sicuri e non schiacciati   |
|☐   |L'ingerito audio su HDMI è funzionale   |
|☐   |L'inserimento di video su HDMI è funzionale   |
|☐   |La console può scorrere liberamente   |



   
## <a name="see-also"></a>Vedere anche
<a name="Checklist"> </a>

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
