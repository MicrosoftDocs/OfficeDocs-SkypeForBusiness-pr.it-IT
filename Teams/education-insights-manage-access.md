---
title: Gestire l'accesso degli utenti a Dati analitici per l'istruzione
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Informazioni su come gestire l'accesso degli utenti a Dati analitici per l'istruzione in Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae8cfa1ea62472255825684d2e168be1411bb643
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604535"
---
# <a name="manage-user-access-to-education-insights"></a>Gestire l'accesso degli utenti a Dati analitici per l'istruzione

Questo documento illustra la procedura necessaria per gestire l'accesso degli utenti a [Dati analitici per l'istruzione in Microsoft Teams](class-insights.md).

È necessario fornire le autorizzazioni per i responsabili dell'istruzione, i dirigenti distrettuali, i presidi scolastici, i dirigenti scolastici, i consulenti, i responsabili delle aree di apprendimento, i direttori dei programmi, gli assistenti sociali e gli psicologi. Ai docenti viene *automaticamente* concessa l'autorizzazione quando sono proprietari di un team di classe.

Per fornire Dati analitici a livello di organizzazione, è necessario [importare i dati dal sistema informativo degli studenti (SIS)](education-insights-sis-data-sync.md) in modo che la struttura gerarchica del sistema didattico di Dati analitici sia mappata correttamente.

> [!NOTE]
> Solo l'amministratore globale può gestire l'accesso degli utenti a Dati analitici.

> [!TIP]
> È consigliabile abilitare Dati analitici per tutti i responsabili della didattica in modo che abbiano a disposizione i dati per conoscere ogni istituto e possano identificare rapidamente i problemi, nonché fornire supporto ai docenti. Anche se si esegue un progetto pilota, può comunque essere utile mantenere Dati analitici abilitato per tutti i responsabili della didattica, impostando però come destinatari delle comunicazioni solo il gruppo pilota di utenti.

## <a name="manange-permissions"></a>Gestire le autorizzazioni

* Aprire l'app Dati analitici, fare clic su **Impostazioni** e selezionare **Autorizzazioni utente**

:::image type="content" source="media/insights-user-permissions.png" alt-text="Impostazioni":::

> [!NOTE]
> Quando si fornisce l'autorizzazione per un livello organizzativo, l'utente può vedere tutte le unità organizzative sottostanti.
> 
> Fornire l'autorizzazione solo ai responsabili della didattica che ne hanno bisogno e solo alle unità organizzative di cui sono responsabili. Se non si è certi che sia necessaria l'autorizzazione dell'utente per una specifica organizzazione, consultare gli esperti in materia di privacy dell'istituto, ad esempio il personale legale o delle risorse umane.

## <a name="role-based-permissions"></a>Autorizzazioni basate sui ruoli

Se si utilizza il [formato di file SDS V2.1](/schooldatasync/sds-v2.1-csv-file-format) o il [formato di file SDS V2](/schooldatasync/sds-v2-csv-file-format), è possibile importare tutti i ruoli e l'intera gerarchia degli istituti di istruzione all'interno del sistema didattico. Questa mappatura completa consente di assegnare autorizzazioni ai ruoli. 

> [!NOTE]
> Quando a un utente viene assegnato un ruolo, riceve automaticamente le giuste autorizzazioni per visualizzare i dati rilevanti.
>
> Se un utente non ha più un ruolo, la sua autorizzazione per quel ruolo viene automaticamente revocata (sebbene possa ancora disporre di autorizzazioni individuali).


* Se necessario, fare clic sulla scheda **Autorizzazioni basate sui ruoli**.

  Verrà visualizzato un elenco dei ruoli nella propria organizzazione didattica, il livello in tale gerarchia per ciascuno, quanti utenti sono assegnati a quel ruolo e il livello di autorizzazione del ruolo. 
  
  :::image type="content" source="media/insights-role-based-permissions.png" alt-text="Autorizzazioni basate sui ruoli":::
  
  Se è presente un ruolo a più di un livello dell'organizzazione, tale ruolo viene visualizzato più volte, una per ogni livello. Nello screenshot, sono presenti presidi sia a livello scolastico che distrettuale, quindi ci sono due righe per "preside".
  
* Per ogni ruolo, fare clic sull'icona a forma di matita per selezionare il livello di autorizzazione. L'impostazione predefinita è che il ruolo non dispone dell'autorizzazione per visualizzare Insights.
* Selezionare il livello di autorizzazione **Visualizza i dati per l'organizzazione** o **Nessuno**.

  :::image type="content" source="media/insights-role-based-permissions-panel.png" alt-text="Pannello delle autorizzazioni basate sui ruoli":::
  
  Se nell'elenco viene visualizzato un utente che necessita di un livello di autorizzazione più complesso, modificare il ruolo e/o l'organizzazione nei [dati importati dal SIS](education-insights-sis-data-sync.md) e [concedere autorizzazioni individuali](#grant-individual-permission-to-a-user) (se necessario).

* Fare clic su **Salva modifiche**.

  Questo livello di autorizzazione viene ora assegnato automaticamente a qualsiasi nuovo utente con questo ruolo e livello di organizzazione. L'utente vedrà i dati per tutte le unità organizzative al suo livello della gerarchia e a un livello sottostante.  


## <a name="individual-permissions"></a>Autorizzazioni individuali

Utilizzare le autorizzazioni individuali per modificare l'autorizzazione per un utente o per assegnare autorizzazioni per ciascun utente se non è stato utilizzato SDS V2 per importare i dati SIS per l'organizzazione.

* Fare clic sulla scheda **Autorizzazioni individuali**.
  
  Verranno visualizzati gli utenti dell'organizzazione didattica che hanno ottenuto l'autorizzazione individuale. 
  
  :::image type="content" source="media/insights-individual-permissions.png" alt-text="Autorizzazioni individuali":::
  
### <a name="grant-individual-permission-to-a-user"></a>Concedere autorizzazioni individuali a un utente
* Fare clic su **Concedi autorizzazione individuale** nella parte superiore sinistra dello schermo.
* Immettere il nome utente o l'indirizzo di posta elettronica di ogni utente.
* Selezionare il livello di autorizzazione:
  * **Tutti** indica che l'utente può visualizzare tutte le unità organizzative a tutti i livelli. Questo livello viene usato molto raramente.
  * **Organizzazione specifica** indica che l'utente vede l'unità organizzativa selezionata e tutte le unità organizzative sottostanti. Iniziare a digitare e selezionare l'unità organizzativa nell'elenco.
* Fare clic su **Concedi autorizzazione** per salvare.

### <a name="change-the-individual-permission-of-a-user"></a>Modificare l'autorizzazione individuale di un utente
* Per l'utente pertinente, fare clic sull'icona a forma di matita per selezionare il livello di autorizzazione individuale.
* Selezionare il livello di autorizzazione:
  * **Tutti** indica che l'utente può visualizzare tutte le unità organizzative a tutti i livelli. Questo livello viene usato molto raramente.
  * **Organizzazione specifica** indica che l'utente vede l'unità organizzativa selezionata e tutte le unità organizzative sottostanti. Iniziare a digitare e selezionare l'unità organizzativa nell'elenco.
  * **Nessuno** indica che l'utente vede solo le unità organizzative assegnate automaticamente dal proprio ruolo (se presenti).
  
  :::image type="content" source="media/insights-individual-permissions-panel.png" alt-text="Pannello delle autorizzazioni individuali":::

* Fare clic su **Salva modifiche** per salvare.
