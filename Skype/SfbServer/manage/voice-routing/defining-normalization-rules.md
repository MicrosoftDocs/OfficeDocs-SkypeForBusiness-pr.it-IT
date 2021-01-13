---
title: Definizione delle regole di normalizzazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Le regole di normalizzazione di Skype for Business Server utilizzano le espressioni regolari di .NET Framework per tradurre i numeri di telefono composti in formato E. 164; in altre parole, le regole di normalizzazione assumono il numero di telefono composto da un utente e convertono tale numero nel formato utilizzato internamente da Skype for Business Server. A ogni dial plan deve essere assegnata una o più regole di normalizzazione.
ms.openlocfilehash: d4e248dc9b814610df544bca9d932a29756a80b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823376"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definizione delle regole di normalizzazione in Skype for Business Server

Le regole di normalizzazione di Skype for Business Server utilizzano le espressioni regolari di .NET Framework per tradurre i numeri di telefono composti in formato E. 164; in altre parole, le regole di normalizzazione assumono il numero di telefono composto da un utente e convertono tale numero nel formato utilizzato internamente da Skype for Business Server. A ogni dial plan deve essere assegnata una o più regole di normalizzazione.

Per informazioni dettagliate sulle regole di normalizzazione, vedere [dial plan e regole di normalizzazione](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx).

Per informazioni dettagliate su come scrivere espressioni regolari, vedere [espressioni regolari di .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).

È possibile utilizzare uno dei metodi seguenti per definire o modificare una regola di normalizzazione:
- [Utilizzare lo strumento **Crea regola di normalizzazione**](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) per specificare i valori per le cifre iniziali, la lunghezza, le cifre da rimuovere e le cifre da aggiungere, quindi lasciare che il pannello di controllo di Skype for Business Server generi il corrispondente modello di corrispondenza e la regola di conversione.
- [Scrivere manualmente espressioni regolari](#create-or-modify-a-normalization-rule-manually) per definire il modello di corrispondenza e la regola di conversione. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Creare o modificare una regola di normalizzazione utilizzando crea una regola di normalizzazione

Se si desidera creare o modificare una regola di normalizzazione nel pannello di controllo di Skype for Business Server, eseguire la procedura seguente. 

**Per definire una regola mediante Crea regola di normalizzazione**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Skype for business, vedere [Install and Open Administrative Tools](../../management-tools/install-and-open-administrative-tools.md).
3. Optional Seguire la procedura descritta in [Create a dial plan](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) through Step 11 o [Modify a dial plan](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) through Step 10. 
4. In **Nuova regola di normalizzazione** o **Modifica regola di normalizzazione** digitare un nome descrittivo del formato del numero da normalizzare in **Nome**, ad esempio **Prefisso5Cifre**.
5. (Facoltativo) In **Descrizione** digitare una descrizione della regola di normalizzazione, ad esempio "Converte prefissi a 5 cifre".
6. In **Crea regola di normalizzazione** immettere valori nei campi seguenti:
    - **Cifre iniziali**: (facoltativo) specificare le cifre iniziali dei numeri composti che si desidera che il modello corrisponda. Digitare ad esempio **425** se si desidera che il formato corrisponda ai numeri composti che iniziano con 425.
    - **Lunghezza**: specificare il numero di cifre nel motivo corrispondente e selezionare se si desidera che il motivo corrisponda esattamente a questa lunghezza, corrispondere ai numeri composti almeno per questa lunghezza o corrispondere a numeri composti di qualsiasi lunghezza.
    - **Cifre da rimuovere**: (facoltativo) specificare il numero di cifre iniziali che devono essere rimosse dai numeri composti che si desidera corrispondano al modello.
    - **Cifre da aggiungere**: (facoltativo) specificare le cifre che devono essere aggiunte ai numeri composti che si desidera corrispondano al modello.
    
    I valori immessi in questi campi vengono riportati nei campi **Formato per corrispondenza** e **Regola di conversione**. Ad esempio, se si lasciano vuote le **cifre iniziali** , digitare **7** nel **campo lunghezza** selezionare **esattamente** e specificare **0** in **cifre da rimuovere**, l'espressione regolare risultante nel **motivo corrispondente** è la seguente:

    **^ (\d {7} ) $**

7. In **Regola di conversione** specificare un modello per il formato dei numeri di telefono E.164 convertiti, come indicato di seguito:
    - Un valore che rappresenta il numero di cifri specificato nel formato della corrispondenza. Ad esempio, se il modello corrispondente è **^ (\d {7} ) $**, allora $1 nella regola di conversione rappresenta numeri composti a 7 cifre.
    - (Facoltativo) Digitare un valore nel campo **Prefisso** per specificare le cifre da anteporre al numero convertito (ad esempio **+1425**).
    
    Ad esempio, se **pattern to match** contiene **^ (\d {7} ) $** come modello per i numeri composti e la **regola di conversione** contiene **+ 1425 $1** come modello per i numeri di telefono e. 164, la regola Normalizza 5550100 in + 14255550100.

8. (Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.
9. (Facoltativo) Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.
    > [!Note] 
    > È possibile salvare una regola di normalizzazione che non passa ancora il test e quindi riconfigurarla successivamente. Per ulteriori informazioni, vedere [test Voice routing](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx). 

10. Fare clic su **OK** per salvare la regola di normalizzazione.
11. Fare clic su **OK** per salvare il dial plan.
12. Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**. 
    > [!Note]
    > Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando Salva tutto per pubblicare la modifica apportata alla configurazione. Per ulteriori informazioni, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Creare o modificare manualmente una regola di normalizzazione

Se si desidera creare o modificare manualmente una regola di normalizzazione, eseguire la procedura seguente.

**Per definire manualmente una regola di normalizzazione**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Skype for business, vedere [Install and Open Administrative Tools](../../management-tools/install-and-open-administrative-tools.md).
3. Optional Seguire la procedura descritta in [Create a dial plan](GET LINK AFTER MIGRATION) through Step 11 o [Modify a dial plan](GET LINK AFTER MIGRATION) through Step 10.  
4. In **nuova regola di normalizzazione** o **Modifica regola di normalizzazione** digitare un nome che descriva il tipo di numero normalizzato in **nome** (ad esempio, denominare la regola di normalizzazione **5DigitExtension**).
5. (Facoltativo) In **Descrizione** digitare una descrizione della regola di normalizzazione, ad esempio "Converte prefissi a 5 cifre".
6. In **genera una regola di normalizzazione** fare clic su **modifica**.
7. Immettere quanto segue in Digita espressione regolare:
    - In **corrispondenza di questo modello** specificare il modello che si desidera utilizzare per la corrispondenza con il numero di telefono composto.
    - In **regola di conversione** specificare un modello per il formato dei numeri di telefono E. 164 tradotti.

    Ad esempio, se si immette **^ (\d {7} ) $** in **corrispondenza di questo modello** e **+ 1425 $1** in **regola di conversione**, la regola Normalizza 5550100 in + 14255550100.

8. (Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.
9. (Facoltativo) Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.

    > [!Note]
    > È possibile salvare una regola di normalizzazione che non passa ancora il test e quindi riconfigurarla successivamente. Per ulteriori informazioni, vedere [test Voice routing](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx). 

10. Fare clic su **OK** per salvare la regola di normalizzazione.
11. Fare clic su **OK** per salvare il dial plan.
12. Nella pagina **dial plan** , fare clic su **commi** t, quindi fare clic su **Salva tutto**. 
