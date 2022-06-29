---
title: Gestire domande&A nelle riunioni di Teams
author: wlibebe
ms.author: wlibebe
ms.reviewer: sameer.sitaram
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
description: Informazioni su come gli amministratori IT possono configurare, usare e gestire le domande&A in Q&A di Teams per un approccio strutturato alla raccolta di domande, all'organizzazione delle discussioni, all'eliminazione di singoli messaggi, all'uso delle lingue disponibili e alla comprensione del ciclo di vita dei dati, nonché dei criteri di conservazione ed eliminazione dei dati.
ms.openlocfilehash: 17de45280809ae6c5fffdce64067fe97020965ec
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494843"
---
# <a name="manage-qa-in-teams-meetings"></a>Gestire domande&A nelle riunioni di Teams

Q&A è un'esperienza di riunione integrata che offre ai partecipanti l'opportunità di chiedere formalmente e ricevere risposte alle domande e di partecipare a discussioni strutturate. Questa esperienza è una procedura consigliata per le riunioni con più di 10 partecipanti.

Questo articolo descrive come gestire i criteri Q&A e a livello utente, che determinano se un organizzatore può abilitare Le domande&A di Teams nelle riunioni.

> [!NOTE]
> Questa funzionalità è attualmente in anteprima privata e non è accessibile pubblicamente. Se desideri partecipare al programma di anteprima privato, iscriviti [qui.](https://m365crmedu.powerappsportals.com/LMSSignup/)


## <a name="prerequisites"></a>Prerequisiti

- Verificare di non aver bloccato [l'accesso agli INDIRIZZI IP e agli URL di Yammer.](/microsoft-365/enterprise/urls-and-ip-address-ranges)
- Per consentire agli utenti dell'organizzazione di aggiungere domande&R alle riunioni di Teams, è necessario verificare che gli accessi per il servizio Office 365 Yammer siano abilitati in Azure Active Directory. Seguire questa procedura per verificare che gli accessi siano abilitati:
  - Passare **all'interfaccia di amministrazione** >  di Azure AD **Tutte le** > **applicazioni** >  Enterprise Office 365 **alle proprietà** di **Yammer** > .
  - Per l'opzione **Abilitato per l'accesso degli utenti?** selezionare **Sì** , se necessario.

## <a name="who-can-use-qa"></a>Chi può usare Q&A

D&A può essere utilizzata dai tipi di utente seguenti:

- Utente normale: utente con credenziali Microsoft 365 nel tuo tenant.
- Utente federato: utente con credenziali Microsoft 365 in un tenant diverso.
- Utente guest: qualsiasi guest aggiunto a Microsoft Teams, SharePoint o Azure Active Directory.

> [!NOTE]
> Q&A al momento non supporta utenti anonimi.

Quando gli amministratori abilitano Q&A, gli utenti con il ruolo organizzatore possono attivare Q&A durante la creazione o l'aggiornamento di riunioni. Tramite le opzioni delle riunioni di Teams e Outlook, gli organizzatori possono anche rimuovere Q&A dalle riunioni in cui è stato precedentemente aggiunto per impedire ai partecipanti di usare la funzionalità.

## <a name="use-the-teams-admin-center-to-manage-qa"></a>Usare l'interfaccia di amministrazione di Teams per gestire le domande&A

> [!NOTE]
> La gestione di Q&A nell'interfaccia di amministrazione non è disponibile nell'anteprima pubblica. Usare PowerShell per configurare e gestire le domande&A per gli utenti.

L'organizzazione potrebbe avere requisiti per limitare gli organizzatori che possono attivare Q&A. È possibile usare l'interfaccia di amministrazione di Teams per gestire quali organizzatori possono attivare Q&A in riunioni di grandi dimensioni.
Segui questi passaggi per controllare quali organizzatori possono usare Q&A:

1. Nell'interfaccia di amministrazione di Teams passare a **Criteri** > [**riunione**](/meeting-policies-participants-and-guests)
2. Selezionare un criterio esistente o crearne uno nuovo e assegnargli un nome, ad esempio "Nessuna Q&A per questi organizzatori"
3. Scorri fino alla sezione **"Partecipanti & Guest",** seleziona disabilita per l'impostazione **"Esperienza di risposta & domande"** e salva il criterio
4. Assegnare il criterio a specifici gruppi, utenti finali o abbonamenti di M365 che si desidera impedire la configurazione di Q&A

## <a name="use-powershell-to-manage-qa"></a>Usare PowerShell per gestire le domande&A

L'organizzazione potrebbe avere requisiti per limitare gli organizzatori che possono attivare Q&A. È possibile usare PowerShell per gestire quali organizzatori possono attivare Q&A in riunioni di grandi dimensioni.

Esempio di comando di PowerShell per abilitare Q&A:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -QnAEngagementMode Enabled
```

## <a name="delete-an-individual-message-from-qa-in-teams"></a>Eliminare un singolo messaggio da Q&A in Teams

Per eliminare una domanda o una risposta pubblicata nell'applicazione Q&A, seguire questa procedura:

1. Accedere al Centro Amministrazione Exchange come amministratore globale.
2. Passare a **Cassette postali** **destinatari** >  e cercare per nome l'utente che ha organizzato la riunione.
3. Selezionare l'organizzatore della riunione e fare clic su **Gestisci delega cassetta postale**. Nella sezione **Lettura e gestione** selezionare **Modifica** > **Aggiungi autorizzazioni**.
4. Aggiungere se stessi come delegato dell'organizzatore della riunione e selezionare Salva.
5. Aprire Calendario di Outlook nel Outlook Web App (non desktop) e selezionare **Aggiungi calendario** e quindi **Aggiungi dalla directory**.
6. Cercare l'organizzatore della riunione e aggiungere il suo calendario ai **miei calendari**. Le riunioni per l'utente selezionato verranno ora visualizzate nel calendario.
7. Nel calendario trovare la riunione per cui si vuole eliminare il contenuto, aprire il record della riunione e selezionare **Chatta con i partecipanti**. Selezionando la chat con i partecipanti si aprirà la chat della riunione in Teams.
8. Passare all'applicazione Q&A nella barra dell'app Teams.
9. Trova le domande o le risposte che vuoi eliminare e seleziona Elimina.
10. Dopo aver eliminato il contenuto, tornare al Centro Amministrazione Exchange e rimuovere se stessi come delegato dell'organizzatore della riunione.

> [!NOTE]
> Se si elimina una domanda prima di rimuovere le risposte, la prima risposta alla domanda diventerà la domanda.
>
> Per evitare questo problema, seguire questa procedura nell'ordine indicato:
>
> 1. Identificare la domanda da eliminare
> 2. Eliminare le risposte alla domanda
> 3. Eliminare la domanda

## <a name="available-languages-for-yammer-versus-teams"></a>Lingue disponibili per Yammer e Teams

La Q&A per impostazione predefinita per la lingua dell'utente per Teams. Quando c'è una differenza tra le lingue disponibili per Teams e Yammer, si verificano le impostazioni predefinite della lingua seguenti:

- Lingua principale più vicina: Per impostazione predefinita, Yammer si trova nella lingua principale più vicina, se disponibile. Ad esempio, Yammer non fornisce una versione francese canadese (fr-CA), quindi visualizzerà il contenuto in francese (fr-FR).
- Lingua non supportata: se la lingua non è disponibile in Yammer, per impostazione predefinita Yammer usa l'inglese (Stati Uniti).

## <a name="ediscovery"></a>eDiscovery

eDiscovery per Q&A funzionerà come eDiscovery per qualsiasi altro contenuto di Yammer.

- Se si usa Teams Q&A nell'applicazione Teams del tenant, questo contenuto sarà disponibile in eDiscovery indipendentemente dalla configurazione o dall'esistenza della rete Yammer. Per usare eDiscovery per il contenuto standard di Yammer, la rete Yammer deve essere in [modalità nativa](/yammer/configure-your-yammer-network/overview-native-mode).
- Quando si esegue eDiscovery, è possibile determinare se i messaggi sono stati generati in Yammer o tramite domande&A in Teams. Nella sezione Metadati file queste informazioni sono disponibili nel campo Classe elemento.
- Se l'organizzazione usa la Q&A di Teams, con tecnologia Yammer, il contenuto generato da Domande&A è considerato contenuto di Yammer e sarà individuabile. Per altre informazioni su eDiscovery nelle app di Microsoft 365, vedere [Soluzioni eDiscovery in Microsoft 365.](/microsoft-365/compliance/ediscovery)

## <a name="data-storage"></a>Archiviazione dei dati

D&I messaggi creati come parte della riunione vengono archiviati come messaggi di Yammer. Questi messaggi vengono archiviati in Yammer e inseriti per eDiscovery.
I file vengono sempre archiviati in SharePoint, che gestisce tutti i criteri e le posizioni di rest dei dati.

Le linee guida seguenti spiegano come vengono archiviati i dati di messaggistica:

- D&Un contenuto è ricercabile tramite eDiscovery e Advanced eDiscovery a livello di utente.
- I dati dei messaggi, che includono il contenuto del messaggio, verranno archiviati in America del Nord o nell'Unione Europea per impostazione predefinita, a seconda del percorso di rete yammer del cliente.
- Per i tenant che non hanno una rete Yammer esistente, la Q&Una rete Yammer verrà creata nell'area Stati Uniti Yammer. I messaggi dell'organizzazione per Q&A verranno sempre archiviati negli Stati Uniti.
- Come per le schede di OneNote, la rimozione della&A da una riunione non comporta l'eliminazione dei dati della riunione. La rimozione di Q&A dalla riunione comporta solo la rimozione dell'accesso ai dati dalla riunione. Se si aggiunge di nuovo la scheda Q&A, verranno nuovamente visualizzate tutte le conversazioni della riunione.

## <a name="gdpr-for-qa-in-teams"></a>GDPR per T&A in Teams

Quando si completa una richiesta dell'interessato tramite il Centro Amministrazione Microsoft 365, le informazioni di contatto degli utenti vengono automaticamente rimosse da tutto il contenuto nella Q&A.

## <a name="data-lifecycle-for-qa-in-teams"></a>Ciclo di vita dei dati per le domande&A in Teams

Il ciclo di vita dei dati generati da Q&A in Teams dipende dalle impostazioni di conservazione dei dati di Yammer nel Centro conformità. Se si eliminano definitivamente tutti gli utenti della riunione che hanno ricevuto una copia dei messaggi Q&A nel supporto del supporto tramite Azure Active Directory, Yammer eliminerà la copia del contenuto Q&A per la riunione entro 30 giorni dall'eliminazione degli utenti.

## <a name="retention-and-deletion"></a>Conservazione ed eliminazione

La conservazione del contenuto segue i criteri di conservazione impostati per Yammer, indipendentemente dal fatto che siano impostati criteri diversi per Yammer e Teams.

> [!NOTE]
> Se la rete Yammer non è in modalità nativa, i criteri creati qui verranno applicati solo ai dati Q&A di Teams. In modalità nativa, tutti gli utenti di Yammer si trovano in Azure Active Directory (Azure AD), tutti i gruppi sono gruppi di Microsoft 365 e tutti i file vengono archiviati in SharePoint Online.

## <a name="faq"></a>Domande frequenti

**D: Ricerca per categorie esportare contenuto Q&A?**

**Un:** D&Un contenuto viene archiviato nel Centro conformità Microsoft 365 e accessibile tramite eDiscovery. Le iterazioni future includeranno un report di evidenziazioni delle riunioni e la funzionalità di esportazione per gli organizzatori delle riunioni.

**D: Q&A supporta le funzionalità Multi-Geo di Microsoft 365?**

**Un:** Q&A attualmente non supporta le funzionalità Multi-Geo di Microsoft 365. D&I dati A verranno archiviati in America del Nord o unione europea per impostazione predefinita, a seconda del percorso di rete di Yammer del cliente.

**D: Dove posso trovare altre informazioni sulle riunioni strutturate?**

**Un:** Seguire queste [procedure consigliate](/MicrosoftTeams/quick-start-meetings-live-events) per organizzare riunioni di grandi dimensioni in Microsoft Teams.

**D: Qual è la differenza tra la configurazione di Q&A tramite Teams App Store e l'uso di Opzioni riunione?**

**Un:** Anche se non c'è differenza tra l'esperienza utente del partecipante e del moderatore, per il futuro è necessario configurare Q&A solo utilizzando opzioni riunione. L'app Q&A nell'app store di Teams sarà deprecata entro la fine del 2022, quindi è consigliabile usare Opzioni riunione per configurare le domande&A nelle riunioni.
