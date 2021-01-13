---
title: Creare o modificare una regola di normalizzazione in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Riepilogo: informazioni su come definire, creare e modificare una regola di normalizzazione in Skype for Business Server.'
ms.openlocfilehash: 6f8619304e9d3d801dfa430e6addb5105a2b82a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830766"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Creare o modificare una regola di normalizzazione in Skype for business

**Riepilogo:** Informazioni su come definire, creare e modificare una regola di normalizzazione in Skype for Business Server.

Definire, creare e modificare le regole di normalizzazione in Skype for Business Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Per definire una regola di normalizzazione utilizzando crea una regola di normalizzazione

1. Aprire il pannello di controllo di Skype for Business Server

2. Optional Seguire la procedura illustrata in [creare o modificare un dial plan in Skype for Business Server](dial-plans.md) tramite il passaggio 11 o [modificare un dial plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) tramite il passaggio 10.

3. In **nuova regola di normalizzazione** o **Modifica regola di normalizzazione** digitare un nome che descriva il tipo di numero normalizzato in **nome** (ad esempio, 5DigitExtension).

4. (Facoltativo) In **Descrizione** digitare una descrizione della regola di normalizzazione, ad esempio "Converte prefissi a 5 cifre".

5. In **Crea regola di normalizzazione** immettere valori nei campi seguenti:

   - **Cifre iniziali** (facoltativo) specificare le cifre iniziali dei numeri composti che si desidera che il modello corrisponda. Ad esempio, type425 se si desidera che il modello corrisponda ai numeri composti che iniziano con 425.

   - **Lunghezza** Specificare il numero di cifre nel motivo corrispondente e selezionare se si desidera che il modello corrisponda esattamente a questa lunghezza, corrispondere a numeri composti che sono almeno questa lunghezza o corrispondere a numeri composti di qualsiasi lunghezza.

   - **Cifre da rimuovere** (facoltativa) specificare il numero di cifre iniziali che devono essere rimosse dai numeri composti che si desidera che il modello corrisponda.

   - **Cifre da aggiungere** (facoltativa) specificare le cifre che devono essere aggiunte ai numeri composti che si desidera corrispondano al modello.

     I valori immessi in questi campi vengono riportati nei campi **Formato per corrispondenza** e **Regola di conversione**. Ad esempio, se si lasciano vuote le **cifre iniziali** , Type7 nel campo **lunghezza** e si seleziona **esattamente** e si specifica 0 in **cifre da rimuovere**, l'espressione regolare risultante nel **modello da corrispondere** è la seguente:

     ^ (\d {7} ) $

6. In **Regola di conversione** specificare un modello per il formato dei numeri di telefono E.164 convertiti, come indicato di seguito:

   - Un valore che rappresenta il numero di cifri specificato nel formato della corrispondenza. Ad esempio, se il modello corrispondente è ^ (\d {7} ) $, $1 nella regola di conversione rappresenta numeri composti a 7 cifre.

   - Optional Digitare un valore nel campo **cifre da aggiungere** per specificare le cifre da anteporre al numero convertito (ad esempio, + 1425).

     Ad esempio, se **pattern to match** contiene ^ (\d {7} ) $ come modello per i numeri composti e la **regola di conversione** contiene + 1425 $1 come modello per i numeri di telefono e. 164, la regola Normalizza 5550100 in + 14255550100.

7. (Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.

8. (Facoltativo) Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.

    > [!NOTE]
    > È possibile salvare una regola di normalizzazione che non passa ancora il test e quindi riconfigurarla successivamente. Per informazioni dettagliate, vedere [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

9. Fare clic su **OK** per salvare la regola di normalizzazione.

10. Fare clic su **OK** per salvare il dial plan.

11. Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per ulteriori informazioni, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.

### <a name="to-define-a-normalization-rule-manually"></a>Per definire manualmente una regola di normalizzazione

1. Aprire il pannello di controllo di Skype for Business Server

2. Optional Seguire la procedura illustrata in [creare o modificare un dial plan in Skype for Business Server](dial-plans.md).

3. In **nuova regola di normalizzazione** o **Modifica regola di normalizzazione** digitare un nome che descriva il tipo di numero normalizzato in **nome** (ad esempio, denominare la normalizzazione rule5DigitExtension).

4. Optional In campo **Descrizione** Digitare una descrizione della regola di normalizzazione (ad esempio, "converte le estensioni a 5 cifre").

5. In **genera una regola di normalizzazione** fare clic su **modifica**.

6. Immettere quanto segue in **Digita espressione regolare**:

   - In **corrispondenza di questo modello** specificare il modello che si desidera utilizzare per la corrispondenza con il numero di telefono composto.

   - In **regola di conversione** specificare un modello per il formato dei numeri di telefono E. 164 tradotti.

     Ad esempio, se si immette ^ (\d {7} ) $ in **corrispondenza di questo modello** e + 1425 $1 in **regola di conversione**, la regola Normalizza 5550100 in + 14255550100.

7. (Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.

8. Optional Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.

9. Fare clic su **OK** per salvare la regola di normalizzazione.

10. Fare clic su **OK** per salvare il dial plan.

11. Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per ulteriori informazioni, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.


