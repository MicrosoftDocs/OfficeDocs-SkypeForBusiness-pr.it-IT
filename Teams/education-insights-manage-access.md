---
title: Gestire l'accesso degli utenti a Dati analitici per l'istruzione
author: DaniEASmith
ms.author: danismith
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
ms.openlocfilehash: 7203c9bda1a6e5c2bf9d90b490492fe7bbc3f64c
ms.sourcegitcommit: 78fbfcf4a1aafce5d39eea79c9461a9fc1bb3d38
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2023
ms.locfileid: "69707808"
---
# <a name="manage-user-access-to-education-insights"></a>Gestire l'accesso degli utenti a Dati analitici per l'istruzione

Questo documento illustra la procedura necessaria per gestire l'accesso degli utenti a [Dati analitici per l'istruzione in Microsoft Teams](class-insights.md).

You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists. Educators are *automatically* given permission when they own a class team.

Per fornire Dati analitici a livello di organizzazione, è necessario [importare i dati dal sistema informativo degli studenti (SIS)](education-insights-sis-data-sync.md) in modo che la struttura gerarchica del sistema didattico di Dati analitici sia mappata correttamente.

> [!NOTE]
> Solo l'amministratore globale può gestire l'accesso degli utenti a Dati analitici.

> [!TIP]
> È consigliabile abilitare Dati analitici per tutti i responsabili della didattica in modo che abbiano a disposizione i dati per conoscere ogni istituto e possano identificare rapidamente i problemi, nonché fornire supporto ai docenti. Anche se si esegue un progetto pilota, può comunque essere utile mantenere Dati analitici abilitato per tutti i responsabili della didattica, impostando però come destinatari delle comunicazioni solo il gruppo pilota di utenti.

## <a name="manage-permissions"></a>Gestione autorizzazioni

* Aprire l'app Dati analitici, fare clic su **Impostazioni** e selezionare **Autorizzazioni utente**

:::image type="content" source="media/insights-user-permissions.png" alt-text="Impostazioni.":::

> [!NOTE]
> Quando si fornisce l'autorizzazione per un livello organizzativo, l'utente può vedere tutte le unità organizzative sottostanti.
> 
> Fornire l'autorizzazione solo ai responsabili della didattica che ne hanno bisogno e solo alle unità organizzative di cui sono responsabili. Se non si è certi che sia necessaria l'autorizzazione dell'utente per una specifica organizzazione, consultare gli esperti in materia di privacy dell'istituto, ad esempio il personale legale o delle risorse umane.

> [!IMPORTANT]
> Dopo aver assegnato le autorizzazioni per la prima volta, gli utenti potranno visualizzare i dati all'interno dell'app solo se almeno **due** utenti hanno eseguito l'accesso all'app. Questo requisito garantisce che il fuso orario per i dati sia configurato correttamente e che i dati vengano visualizzati in modo accurato per tutti gli utenti. Se gli utenti hanno problemi ad accedere ai dati dopo aver concesso le autorizzazioni, verificare se almeno due utenti hanno eseguito l'accesso all'app.

## <a name="role-based-permissions"></a>Autorizzazioni basate sui ruoli

If you use [SDS V2.1 file format](/schooldatasync/sds-v2.1-csv-file-format) or [SDS V2 file format](/schooldatasync/sds-v2-csv-file-format), you can import all roles and the full hierarchy of schools within the education system. This complete mapping enables you to assign permissions to roles. 

> [!NOTE]
> Quando a un utente viene assegnato un ruolo, riceve automaticamente le giuste autorizzazioni per visualizzare i dati rilevanti.
>
> Se un utente non ha più un ruolo, la sua autorizzazione per quel ruolo viene automaticamente revocata (sebbene possa ancora disporre di autorizzazioni individuali).

* Se necessario, fare clic sulla scheda **Autorizzazioni basate sui ruoli**.

  Verrà visualizzato un elenco dei ruoli nella propria organizzazione didattica, il livello in tale gerarchia per ciascuno, quanti utenti sono assegnati a quel ruolo e il livello di autorizzazione del ruolo. 
  
  :::image type="content" source="media/insights-role-based-permissions.png" alt-text="Autorizzazioni basate sui ruoli.":::
  
  Se è presente un ruolo a più di un livello dell'organizzazione, tale ruolo viene visualizzato più volte, una per ogni livello. Nello screenshot, sono presenti presidi sia a livello scolastico che distrettuale, quindi ci sono tre righe per "preside".
  
* Per ogni ruolo, fare clic sull'icona a forma di matita per selezionare il livello di autorizzazione. L'impostazione predefinita è che il ruolo non dispone dell'autorizzazione per visualizzare Insights.
* Selezionare il livello di autorizzazione **Visualizza i dati per l'organizzazione** o **Nessuno**.

  :::image type="content" source="media/insights-role-based-permissions-panel.png" alt-text="Pannello delle autorizzazioni basate sui ruoli.":::
  
  Se nell'elenco viene visualizzato un utente che necessita di un livello di autorizzazione più complesso, modificare il ruolo e/o l'organizzazione nei [dati importati dal SIS](education-insights-sis-data-sync.md) e [concedere autorizzazioni individuali](#grant-individual-permission-to-a-user) (se necessario).

* Fare clic su **Salva modifiche**.

  Questo livello di autorizzazione viene ora assegnato automaticamente a qualsiasi nuovo utente con questo ruolo e livello di organizzazione. L'utente vedrà i dati per tutte le unità organizzative al suo livello della gerarchia e a un livello sottostante.  


## <a name="individual-permissions"></a>Autorizzazioni individuali

Utilizzare le autorizzazioni individuali per modificare l'autorizzazione per un utente o per assegnare autorizzazioni per ciascun utente se non è stato utilizzato SDS V2 per importare i dati SIS per l'organizzazione.

* Fare clic sulla scheda **Autorizzazioni individuali**.
  
  Verranno visualizzati gli utenti dell'organizzazione didattica che hanno ottenuto l'autorizzazione individuale. 
  
  :::image type="content" source="media/insights-individual-permissions.png" alt-text="Autorizzazioni individuali.":::
  
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
  
  :::image type="content" source="media/insights-individual-permissions-panel.png" alt-text="Pannello delle autorizzazioni individuali.":::

* Fare clic su **Salva modifiche** per salvare.
