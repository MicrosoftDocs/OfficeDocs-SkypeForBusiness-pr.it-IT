---
title: Definizione delle regole di conversione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server Enterprise Voice instrada le chiamate in base ai numeri di telefono normalizzati nel formato E. 164. Questo significa che tutte le stringhe commutate devono essere normalizzate nel formato E. 164 allo scopo di eseguire la ricerca di numeri inversi (inversa), in modo che possano essere convertite nell'URI SIP corrispondente. Skype for Business Server offre la possibilità di modificare l'ID chiamato e la presentazione dell'ID chiamante.
ms.openlocfilehash: 49598c2ef6b1a145c206bece3e06068067b0a0e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151206"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definizione delle regole di conversione in Skype for Business Server

Skype for Business Server Enterprise Voice instrada le chiamate in base ai numeri di telefono normalizzati nel formato E. 164. Questo significa che tutte le stringhe commutate devono essere normalizzate nel formato E. 164 allo scopo di eseguire la ricerca di numeri inversi (inversa), in modo che possano essere convertite nell'URI SIP corrispondente. Skype for Business Server offre la possibilità di modificare l'ID chiamato e la presentazione dell'ID chiamante.

Con Skype for Business Server, il numero di telefono della parte chiamata (ovvero il numero di telefono chiamato) può essere convertito dal formato E. 164 al formato di composizione locale richiesto dal peer trunk, ovvero il gateway associato, il PBX (Private Branch Exchange) o il SIP trunk). A tale scopo, è necessario definire una o più regole per la conversione dell'URI di richiesta prima del routing al peer trunk.

## <a name="caller-id-presentation"></a>Presentazione dell'ID chiamante

Skype for Business Server offre la possibilità di tradurre anche il numero di telefono della parte chiamante (ovvero il numero di telefono da cui il chiamante chiama) dal formato E. 164 al formato di composizione locale richiesto dal peer trunk. È ad esempio possibile scrivere una regola di conversione per rimuovere +44 da una stringa di composizione e sostituirlo con 0144.

**Per configurare l'ID chiamante tramite il pannello di controllo di Skype for Business Server**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Skype for business, vedere [Install and Open Administrative Tools](../../management-tools/install-and-open-administrative-tools.md).
3. Nella barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Configurazione trunk**.
4. Nella pagina Configurazione trunk fare doppio clic su un trunk esistente, ad esempio il trunk **Globale** per visualizzare la finestra di dialogo **Modifica configurazione trunk**.
5. Per configurare la presentazione dell'ID chiamante:
    - Per selezionare una o più regole in un elenco di tutte le regole di conversione disponibili nella distribuzione di VoIP aziendale, fare clic su **Seleziona**. In **Regola di conversione per il numero del chiamante** fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.
    - Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**. 
    - Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**.
    - Per copiare una regola di conversione esistente da utilizzare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola, scegliere **copia**e quindi fare clic su **Incolla**.
    - Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.

> [!Warning] 
> Non associare regole di conversione a un trunk se sono state configurate regole di conversione nel peer trunk associato, perché le due regole potrebbero essere in conflitto. 

## <a name="called-id-presentation"></a>Presentazione ID chiamata

> [!Important]
> La possibilità di associare una o più regole di conversione a una configurazione trunk VoIP aziendale è destinata a essere utilizzata come *alternativa* alla configurazione delle regole di conversione nel peer trunk. Non associare regole di conversione a una configurazione trunk VoIP aziendale se sono state configurate regole di conversione nel peer trunk perché le due regole potrebbero essere in conflitto. 

È possibile utilizzare uno dei metodi seguenti per creare e modificare una regola di conversione:

- [Utilizzare lo strumento Crea regola di conversione](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) per specificare i valori per le cifre iniziali, la lunghezza, le cifre da rimuovere e le cifre da aggiungere, quindi lasciare che il pannello di controllo di Skype for Business Server generi la corrispondente regola di conversione e il modello corrispondenti.
- [Scrivere manualmente espressioni regolari](#create-or-modify-a-translation-rule-manually) per definire il modello di corrispondenza e la regola di conversione.

> [!Note]
> Per informazioni su come scrivere espressioni regolari, vedere [espressioni regolari di .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Creare o modificare una regola di conversione utilizzando lo strumento Crea regola di conversione

Seguire questa procedura se si desidera definire una regola di conversione immettendo un insieme di valori nello strumento Crea regola di conversione e consentendo al pannello di controllo di Skype for Business Server di generare per l'utente il modello corrispondente e la regola di conversione corrispondenti. 

**Per definire una regola tramite lo strumento Crea regola di conversione**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Skype for business, vedere [Install and Open Administrative Tools](../../management-tools/install-and-open-administrative-tools.md).
3. Per iniziare a definire una regola di conversione, eseguire la procedura descritta in [Configure a Trunk with media bypass](GET LINK AFTER MIGRATION)through Step 10 o [Configure a Trunk Without Media Bypass](GET LINK AFTER MIGRATION) through Step 9.
4. In **Nome** nella pagina **Nuova regola di conversione** o **Modifica regola di conversione** digitare un nome descrittivo del formato del numero da convertire.
5. Optional In **Descrizione**Digitare una descrizione della regola di conversione, ad esempio le **chiamate interurbane internazionali degli Stati Uniti**.
6. Nella sezione **Crea regola di conversione** della finestra di dialogo immettere i valore nei campi seguenti:
    - **Cifre iniziali**: (facoltativo) specificare le cifre iniziali dei numeri a cui si desidera corrisponda il formato. Ad esempio, immettere + in questo campo per specificare una corrispondenza con i numeri nel formato E.164, che iniziano con +.
    - **Lunghezza**: specificare il numero di cifre nel formato e specificare se si desidera applicare il formato ai numeri esattamente di questa lunghezza, almeno di questa lunghezza o di qualsiasi lunghezza. Ad esempio, immettere **11** e selezionare **Almeno** nell'elenco a discesa per specificare una corrispondenza con i numeri con una lunghezza di almeno 11 cifre.
    - **Cifre da rimuovere**: (facoltativo) specificare il numero di cifre iniziali da rimuovere. Ad esempio, immettere **1** per rimuovere il + all'inizio del numero.
    - **Prefisso**: (facoltativo) specificare le cifre da aggiungere all'inizio dei numeri convertiti. Ad esempio, immettere **011** se si desidera aggiungere 011 all'inizio dei numeri convertiti quando si applica questa regola.
    
    I valori immessi in questi campi sono riportati nel **modello per la corrispondenza** e la **conversione** dei campi delle regole. Ad esempio, se si specificano i valori di esempio precedenti, l'espressione regolare risultante nel campo **pattern to matc**h è:
    
    **^\+(\d{9}\d +) $** 

    Nel campo **Regola di conversione** specificare un modello per il formato dei numeri convertiti. Il modello è composto da due parti:
    - Un valore (ad esempio **$1**) che rappresenta il numero di cifre nel formato corrispondente
    - (Facoltativo) Un valore che è possibile aggiungere all'inizio del numero immettendolo nel campo **Prefisso**

    In base ai valori di esempio precedenti, nel campo **Regola di conversione** viene visualizzato **011$1**.
    
    Con l'applicazione di questa regola di conversione il numero +441235551010 diventa 011441235551010.
7. Fare clic su **OK** per salvare la regola di conversione.
8. Fare clic su **OK** per salvare la configurazione del trunk.
9. Nella pagina **trunk configuratio**n fare clic su **commit**e quindi su **Salva tutto**. 

> [!Note]
> Ogni volta che si crea o modifica una regola di conversione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per ulteriori informazioni, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Creare o modificare manualmente una regola di conversione

Eseguire questa procedura se si desidera definire una regola di conversione scrivendo un'espressione regolare per il formato e la regola. 

**Per definire manualmente una regola di conversione**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Skype for business, vedere [Install and Open Administrative Tools](../../management-tools/install-and-open-administrative-tools.md).
3. Per iniziare a definire una regola di conversione, eseguire la procedura descritta in [Configure a Trunk with media bypass](GET LINK AFTER MIGRATION)through Step 10 o [Configure a Trunk Without Media Bypass](GET LINK AFTER MIGRATION) through Step 9.
4. Nel campo **Nome** della pagina **Nuova regola di conversione** o **Modifica regola di conversione** digitare un nome che descriva il formato del numero da convertire.
5. Optional In **Descrizione**Digitare una descrizione della regola di conversione. ad esempio, le **chiamate interurbane internazionali degli Stati Uniti**.
6. Fare clic su **Modifica** nella parte inferiore della sezione **Crea regola di conversione**.
7. Immettere quanto segue in digitare un' **espressione regolare**:
    - In **Trova corrispondenza per questo formato** specificare il modello di formato da utilizzare per trovare corrispondenze con i numeri da convertire.
    - In **Regola di conversione** specificare un modello per il formato dei numeri convertiti.

    Ad esempio, se si immette ** ^ \+(\d{9}\d +) $** in **corrispondono a questo modello** e **011 $1** in **regola di conversione**, la regola verrà convertita da + 441235551010 a 011441235551010.
8. Fare clic su **OK** per salvare la regola di conversione.
9. Fare clic su **OK** per salvare la configurazione del trunk.
10. Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**. 

> [!Note] 
> Ogni volta che si crea o modifica una regola di conversione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per ulteriori informazioni, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). 
