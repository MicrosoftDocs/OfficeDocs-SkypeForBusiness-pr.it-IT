---
title: Gestire Microsoft Teams Rooms.
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Informazioni su come sviluppare ed eseguire interventi di manutenzione e operazioni continuativi per garantire che i sistemi Microsoft Teams Rooms siano disponibili per gli utenti.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47f1c170fd0c41331dfaffa2d81386ac3c2fb722
ms.sourcegitcommit: 0967f725aad0a7b9c430b2e30a37ea333007558a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "65106271"
---
# <a name="manage-microsoft-teams-rooms"></a>Gestire Microsoft Teams Rooms.

Se nell'organizzazione sono presenti Microsoft Teams Rooms, sono disponibili opzioni di gestione flessibili.  È possibile gestire i dispositivi autonomamente nella stessa posizione centrale in cui si gestiscono tutte le soluzioni Teams, Microsoft Teams interfaccia di amministrazione. In alternativa, è possibile trasferire la responsabilità di gestione a esperti dedicati usando [Microsoft Teams Rooms Servizi gestiti](https://portal.rooms.microsoft.com).  È anche possibile delegare l'accesso di gestione a un partner di propria scelta per una delle opzioni.

Con Microsoft Teams'interfaccia di amministrazione è possibile:

- Eseguire la gestione dei dispositivi, ad esempio riavviare i dispositivi e scaricare i log dei dispositivi
- Applicare Teams impostazioni specifiche
- Controllare lo stato di integrità di Microsoft Teams Rooms e delle relative periferiche, incluse fotocamere, schermi, microfoni e così via
- Esaminare le attività delle riunioni attuali e passate, ad esempio i dettagli sulla qualità delle chiamate, l'integrità e la connettività di rete e il numero di partecipanti.
- Vedi le periferiche (ad esempio fotocamere e proiettori) collegate a Microsoft Teams Rooms

Per gestire Teams Rooms dispositivi, apri l'interfaccia di [amministrazione di Microsoft Teams](https://admin.teams.microsoft.com) e passa a **Dispositivi** >  Teams **Teams Rooms in Windows**.

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="Teams Rooms pagina di riepilogo nell'interfaccia di amministrazione di Teams.":::


> [!IMPORTANT]
> Per gestire i dispositivi usando l'interfaccia di amministrazione di Teams, è necessario avere i ruoli Amministratore globale, Amministratore Teams o Amministratore dispositivi Teams.

## <a name="make-changes-to-teams-rooms-devices"></a>Apportare modifiche ai dispositivi Teams Rooms

Se hai più di un Teams Rooms, puoi eseguire la maggior parte delle azioni su più dispositivi contemporaneamente. Ad esempio, è possibile impostare Teams impostazioni dell'app in tutti i Teams Rooms contemporaneamente.

### <a name="device-settings"></a>Impostazioni dispositivo

È possibile modificare le impostazioni in uno o più Teams Rooms dell'organizzazione. Per modificare le impostazioni, seleziona il dispositivo o i dispositivi che vuoi gestire e quindi seleziona **Modifica Impostazioni**. Verrà aperto un nuovo riquadro con tutte le impostazioni modificabili. La tabella seguente elenca le impostazioni che è possibile modificare usando l'interfaccia di amministrazione di Teams. Alcune impostazioni sono disponibili solo quando si seleziona una singola Teams Rooms.

Se si selezionano più impostazioni, le impostazioni che supportano la modifica in blocco mostrano le due opzioni seguenti.

- **Mantenere un valore esistente** Se si sceglie questa opzione, non verrà apportata alcuna modifica all'impostazione nella Teams Rooms selezionata.
- **Sostituisci il valore esistente con** Se si sceglie questa opzione, è possibile aggiornare l'impostazione nel Teams Rooms selezionato con il valore specificato.
    > [!CAUTION]
    > I valori esistenti nelle impostazioni che si sceglie di aggiornare verranno sostituiti con il valore specificato. Se si vuole aggiungere un valore a un elenco di valori esistenti, è necessario includere i valori esistenti con il valore da sommare. Ad esempio, se un'impostazione ha un elenco di domini esistente di `contoso.com, fabrikam.com`e si vuole aggiungere `northwindtraders.com`, il valore da fornire sarà `contoso.com, fabrikam.com, northwindtraders.com`.
    >
    > Se selezioni più Teams Rooms, l'impostazione in tutti i dispositivi selezionati verrà impostata sul valore specificato. Se Teams Rooms hanno valori diversi per un'impostazione, verranno tutti aggiornati allo stesso valore.

| Impostazione                                                      | Valori accettati                                        | Supporta la modifica in blocco |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *Account*                                                    |                                                        |                    |
| **Posta elettronica**                                                    | Indirizzo email                                          | No                 |
| **Modalità riunione supportata**                                   | solo Microsoft Teams<br>Skype for Business (impostazione predefinita) e Microsoft Teams<br>Skype for Business e Microsoft Teams (impostazione predefinita)<br>solo Skype for Business|Sì|
| **Autenticazione moderna**                                    | Attivato<br>Disattivato                                              | Sì                |
| **indirizzo Exchange**                                         | Indirizzo email                                          | No                 |
| **Dominio\nomeutente (facoltativo)**                               | Dominio account e nome utente                           | No                 |
| **Configurare il dominio**                                         | Elenco separato da virgole                                   | Sì                |
| *Riunioni*                                                   |                                                        |                    |
| **Condivisione automatica dello schermo**                                 | Attivato<br>Disattivato                                              | Sì                |
| **Condivisione audio in ingresso HDMI**                                 | Attivato<br>Disattivato                                              | Sì                |
| **Visualizzare i nomi delle riunioni**                                       | Attivato<br>Disattivato                                              | Sì                |
| **Uscita automatica se tutti gli altri hanno lasciato la riunione**                 | Attivato<br>Disattivato                                              | Sì                |
| **Partecipare a riunioni di terze parti**                 | Cisco Webex<br>Zoom                                              | Sì                |
| **Partecipare con le informazioni sulla sala**                 | Selezionato<br>Deselezionata                                              | Sì                |
| **Partecipa con info personalizzate**                 | Selezionato<br>Deselezionata                                              | Sì                |
| **Nome (obbligatorio)**                 | Nome della stanza o dello spazio                                              | Sì                |
| **E-mail (obbligatorio)**                 | Indirizzo email                                              | Sì                |
| *Dispositivo*                                                     |                                                        |                    |
| **Modalità doppio monitor**                                        | Attivato<br>Disattivato                                              | Sì                |
| **Consentire la duplicazione del contenuto** | Selezionato<br>Deselezionata                                 | Sì                |
| **Bluetooth beaconing**                                      | Attivato<br>Disattivato                                              | Sì                |
| **Accettare automaticamente inviti alle riunioni in base alla prossimità** | Selezionato<br>Deselezionata                                 | Sì                |
| **Inviare log con feedback**                                  | Attivato<br>Disattivato                                              | Sì                |
| **Indirizzo di posta elettronica per i log e feedback**                      | Indirizzo email                                          | Sì                |
| *Coordinare riunioni*                                                     |                                                        |                    |
| **Riunioni coordinate** | Attivato<br>Disattivato                                 | No                |
| **Attivare il microfono del dispositivo** | Attivato<br>Disattivato                                 | No                |
| **Consentire agli utenti di abilitare l'accesso a una riunione** | Selezionato<br>Deselezionata                                 | No                |
| **Attivare la fotocamera del dispositivo** | Attivato<br>Disattivato                                 | No                |
| **Consentire agli utenti di abilitare l'accesso a una riunione** | Selezionato<br>Deselezionata                                 | No                |
| **Attivare la lavagna per questo dispositivo** | Attivato<br>Disattivato                                 | No                |
| **Account di dispositivo attendibili (separati da virgole)** | Elenco dei dispositivi                              | No                |
| *Periferiche*                                                |                                                        |                    |
| **Microfono per conferenze**                                  | Elenco dei microfoni disponibili                          | No                 |
| **Altoparlante conferenza**                                     | Elenco degli altoparlanti disponibili                             | No                 |
| **Volume predefinito**                                           | 0-100                                                  | No                 |
| **Altoparlante predefinito**                                          | Elenco degli altoparlanti disponibili                             | No                 |
| **Volume predefinito**                                           | 0-100                                                  | No                 |
| **Fotocamera contenuto**                                           | Elenco delle fotocamere disponibili                              | No                 |
| **Miglioramenti apportati alla fotocamera contenuto**                              | Attivato<br>Disattivato                                              | No                 |
| **Ruotare la fotocamera del contenuto di 180 gradi**                        | Attivato<br>Disattivato                                              | No                 |
| *Temi*                                                    |                                                        |                    |
|                                                              | Predefinito<br>Nessun tema<br>Personalizzato<br>Elenco di temi predefiniti   | Sì                |

### <a name="cortana-settings"></a>Cortana impostazioni

È possibile abilitare Cortana per _l'attivazione vocale_ o _push per parlare_ con PowerShell per tutti i dispositivi dell'organizzazione o per ogni dispositivo separatamente.

Vedere [Microsoft Teams Rooms su Windows](../cortana-in-teams.md) nell'articolo "Cortana assistenza vocale in Teams".

### <a name="front-row-layout-settings"></a>Impostazioni del layout Prima riga

La prima riga è l'opzione di layout della visualizzazione riunione per Teams Rooms in Windows.

| Teams dispositivo | Versione dell'app | Davanti al display della sala |
|--------------|-------------|-----------------------|
|Microsoft Teams Rooms su Windows | 4.11.12.0 o versione successiva (è consigliata la versione più recente) | Supporta display singoli e doppi; Dimensioni minime: 46 pollici; Proporzioni 16:9 con risoluzione 1920x1080 o 21:9 con risoluzione 2560x1080; Tutti gli schermi devono essere impostati con ridimensionamento al 100% nelle impostazioni di Windows |

Vedere [Microsoft Teams Rooms manutenzione e le operazioni](rooms-operations.md#scale-and-resolution), per modificare le impostazioni dello schermo in modo da soddisfare i requisiti di Front row.

Per informazioni su come impostare Front row come layout predefinito per una chat room o su come disattivarlo, vedere [Gestire in remoto le impostazioni di una console Microsoft Teams Rooms con un file di configurazione XML](xml-config-file.md#set-front-row-as-the-default-layout).

Per altre informazioni sulla gestione di Front Row, vedere [Problemi noti](known-issues.md#Limits) .

## <a name="device-restart-options"></a>Opzioni di riavvio del dispositivo

Le modifiche alle impostazioni del dispositivo avranno effetto solo dopo il riavvio di Teams Rooms. Quando apporti modifiche che richiedono un riavvio, puoi scegliere se riavviarlo immediatamente o pianificare un riavvio. Ecco le opzioni di riavvio disponibili:

- **Riavvio immediato** Se scegli questa opzione, tutti i dispositivi a cui stai apportando modifiche verranno riavviate non appena selezioni questa opzione.
- **Riavvio pianificato** Se scegli questa opzione, puoi riavviare i dispositivi a cui stai apportando modifiche in un momento meno fastidioso per l'organizzazione.
  - **Seleziona data e ora** : scegli la data e l'ora specifiche per riavviare il dispositivo. La data e l'ora scelte sono locali per il dispositivo da riavviare. 
  - **Lascia l'aggiornamento per il riavvio notturno** I dispositivi vengono riavviati ogni notte per eseguire la manutenzione. Le modifiche apportate ai dispositivi verranno applicate durante questo riavvio.

> [!CAUTION]
> Teams Rooms in uso al momento del riavvio non saranno disponibili per la durata del processo di riavvio. Verranno disconnessi dalle riunioni in corso e non saranno disponibili per partecipare a nuove riunioni.

## <a name="remove-device"></a>Rimuovi dispositivo

Quando si rimuove un dispositivo, il dispositivo viene rimosso dall'organizzazione e non viene più visualizzato nell'elenco di Teams Rooms in Windows nell'interfaccia di amministrazione di Teams.

Se rimuovi un dispositivo che è ancora configurato con un nome utente e una password validi, verrà aggiunto di nuovo automaticamente all'elenco Teams Rooms se si connette nuovamente a Microsoft 365.

Per rimuovere uno o più dispositivi, eseguire le operazioni seguenti:

1. Vai a **Teams Dispositivi** >  **Teams Rooms in Windows** e seleziona i dispositivi che vuoi rimuovere.
2. Seleziona **Rimuovi**.

## <a name="download-device-logs"></a>Scaricare i log dei dispositivi

Se richiesto dal supporto tecnico Microsoft, è possibile scaricare una copia dei file di log diagnostici di un dispositivo. I file di log vengono compressi in un file ZIP che può essere scaricato dall'interfaccia di amministrazione di Teams.

Per scaricare i log da un dispositivo Teams Rooms nel computer, eseguire le operazioni seguenti:

1. Passare a **Teams Dispositivi** >  **Teams Rooms in Windows** e selezionare il nome del dispositivo da cui scaricare i log.
1. Selezionare **Scarica registri dispositivi**. La disponibilità dei log dei dispositivi può richiedere alcuni minuti.
1. Selezionare la scheda **Cronologia** e quindi selezionare il collegamento al file di log in **File di diagnostica**. Nella cartella Download predefinita del browser verrà scaricato un file ZIP contenente i file di log diagnostici del dispositivo.

## <a name="view-device-information"></a>Visualizzare le informazioni sul dispositivo

Dall'Teams interfaccia di amministrazione è possibile visualizzare lo stato generale di tutti i dispositivi dell'organizzazione e visualizzare i dettagli di ogni dispositivo singolarmente.

### <a name="teams-rooms-system-dashboard"></a>dashboard di sistema Teams Rooms

Il dashboard di sistema Teams Rooms mostra a colpo d'occhio lo stato e l'integrità di tutti i dispositivi.

### <a name="device-details-view"></a>Visualizzazione dettagli dispositivo

Per visualizzare informazioni dettagliate su un dispositivo, selezionane il nome nell'elenco dei dispositivi. Nella visualizzazione dettagli, è possibile visualizzare le informazioni seguenti sul dispositivo:

- **Stato di integrità** Mostra l'integrità generale del dispositivo sala Teams. Lo stato di integrità può essere **Sano** o **Non sano**.
- **Offline da** Mostra l'ultima volta che Microsoft 365 è riuscito a comunicare con il dispositivo.
- **Stato dispositivo** Mostra lo stato corrente del dispositivo: **Inattivo**, **Riunione Teams**, **Riunione Skype** o **Ingest**.
- **Periferiche** Mostra le periferiche connesse al dispositivo Teams Room e il relativo stato di integrità. Lo stato di integrità può essere **Connesso** o **Disconnesso**.
- **Salute** Mostra informazioni dettagliate sulle periferiche connesse al dispositivo Teams Room, sulla connettività di rete, sullo stato di accesso ai servizi necessari e sulle informazioni sulla versione del software.
- **Dettagli** Mostra le informazioni sul produttore, l'indirizzo IP di rete e Teams indirizzo seriale/MAC del dispositivo sala.
- **Attività** Mostra i dettagli della riunione passati, tra cui data e ora della riunione, numero di partecipanti, durata e qualità audio. Per altre informazioni sui dettagli delle riunioni, vedere la sezione [Dettagli attività riunione](#meeting-activity-details) più avanti in questo articolo.
- **Storia** Mostra una cronologia delle attività di gestione nel dispositivo sala Teams, inclusi gli aggiornamenti di configurazione, i riavvii dei dispositivi e i collegamenti per il download del log dei dispositivi.

#### <a name="meeting-activity-details"></a>Dettagli attività riunione

La scheda **Attività** in Teams Dettagli dispositivo sala mostra informazioni dettagliate e di alto livello su tutte le riunioni a cui il dispositivo ha partecipato nel tempo. Nella scheda **Attività** è possibile vedere quando si è tenuta una riunione, quanti partecipanti hanno partecipato alla riunione e la qualità dell'audio durante la riunione.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams elenco di riepilogo delle attività dei dispositivi della sala.":::

Per visualizzare le informazioni dettagliate su una riunione specifica, selezionare la data e l'ora della riunione per cui si vogliono ottenere altre informazioni. Se una riunione include solo due partecipanti, verrà visualizzata la pagina dei dettagli del partecipante, altrimenti verrà visualizzata una pagina di riepilogo dei partecipanti.

##### <a name="participant-summary"></a>Riepilogo dei partecipanti

La pagina di riepilogo dei partecipanti mostra tutti i partecipanti che hanno partecipato alla riunione. È possibile vedere quando ogni partecipante ha eseguito l'accesso alla riunione, il nome, la qualità dell'audio e le funzionalità usate durante la sessione. Per visualizzare i dettagli della sessione di un partecipante, selezionare l'ora di inizio della sessione per tale partecipante.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams dettagli sulla conferenza del dispositivo room.":::

##### <a name="participant-details"></a>Dettagli partecipante

La pagina dei dettagli del partecipante mostra le informazioni diagnostiche end-to-end per la sessione del partecipante. Come illustrato nell'immagine seguente, le informazioni **su dispositivo**, **sistema** e **connettività** vengono fornite per il partecipante e per il dispositivo Teams Rooms. **Vengono** fornite anche informazioni diagnostiche di rete tra il partecipante e il dispositivo Teams Rooms. Selezionare l'icona per il contesto su cui si vogliono altre informazioni. Per altre informazioni di diagnostica, seleziona la scheda **Avanzate** .

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams i dettagli della chiamata al dispositivo della sala.":::
