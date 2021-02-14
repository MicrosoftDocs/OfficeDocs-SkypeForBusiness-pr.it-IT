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
description: Le regole di normalizzazione di Skype for Business Server usano le espressioni regolari di .NET Framework per convertire i numeri di telefono composto nel formato E.164; in altre parole, le regole di normalizzazione prendono il numero di telefono composto da un utente e convertono tale numero nel formato utilizzato internamente da Skype for Business Server. A ogni dial plan deve essere assegnata una o più regole di normalizzazione.
ms.openlocfilehash: d4e248dc9b814610df544bca9d932a29756a80b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823376"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definizione delle regole di normalizzazione in Skype for Business Server

Le regole di normalizzazione di Skype for Business Server usano le espressioni regolari di .NET Framework per convertire i numeri di telefono composto nel formato E.164; in altre parole, le regole di normalizzazione prendono il numero di telefono composto da un utente e convertono tale numero nel formato utilizzato internamente da Skype for Business Server. A ogni dial plan deve essere assegnata una o più regole di normalizzazione.

Per informazioni dettagliate sulle regole di normalizzazione, vedere [Dial plan e regole di normalizzazione.](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx)

Per informazioni dettagliate su come scrivere espressioni regolari, vedere [Espressioni regolari di .NET Framework.](https://go.microsoft.com/fwlink/p/?linkId=140927)

È possibile utilizzare uno dei metodi seguenti per definire o modificare una regola di normalizzazione:
- Utilizzare lo strumento Crea regola di [ **normalizzazione**](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) per specificare i valori per le cifre iniziali, la lunghezza, le cifre da rimuovere e le cifre da aggiungere, quindi lasciare che il Pannello di controllo di Skype for Business Server generi automaticamente il modello di corrispondenza e la regola di conversione corrispondenti.
- [Scrivere manualmente espressioni regolari per](#create-or-modify-a-normalization-rule-manually) definire il modello di corrispondenza e la regola di conversione. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Creare o modificare una regola di normalizzazione utilizzando Crea regola di normalizzazione

Completare i passaggi seguenti se si desidera creare o modificare una regola di normalizzazione nel Pannello di controllo di Skype for Business Server. 

**Per definire una regola mediante Crea regola di normalizzazione**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [Delegare le autorizzazioni di installazione.](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo. Per informazioni dettagliate sui diversi metodi che puoi usare per avviare il Pannello di controllo di Skype for Business, vedi [Installare e aprire gli strumenti di amministrazione.](../../management-tools/install-and-open-administrative-tools.md)
3. (Facoltativo) Seguire i passaggi descritti in [Creare un dial plan](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) fino al passaggio 11 o modificare un dial plan fino [al](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) passaggio 10. 
4. In **Nuova regola di normalizzazione** o **Modifica regola di normalizzazione** digitare un nome descrittivo del formato del numero da normalizzare in **Nome**, ad esempio **Prefisso5Cifre**.
5. (Facoltativo) In **Descrizione** digitare una descrizione della regola di normalizzazione, ad esempio "Converte prefissi a 5 cifre".
6. In **Crea regola di normalizzazione** immettere valori nei campi seguenti:
    - **Cifre iniziali**: (Facoltativo) Specificare le cifre iniziali dei numeri composto a cui si desidera che il formato corrisponda. Digitare ad esempio **425** se si desidera che il formato corrisponda ai numeri composti che iniziano con 425.
    - **Lunghezza**: specificare il numero di cifre nel formato corrispondente e specificare se si desidera che il formato corrisponda esattamente a questa lunghezza, che corrisponda ai numeri composto almeno di questa lunghezza o che corrispondano a numeri di qualsiasi lunghezza.
    - **Cifre da rimuovere**: (Facoltativo) Specificare il numero di cifre iniziale da rimuovere dai numeri composto a cui si desidera che il formato corrisponda.
    - **Cifre da aggiungere**: (Facoltativo) Specificare le cifre da aggiungere ai numeri composto a cui si desidera che il formato corrisponda.
    
    I valori immessi in questi campi vengono riportati nei campi **Formato per corrispondenza** e **Regola di conversione**. Se ad esempio  si lasciano vuote le cifre  di inizio, digitare **7** nel campo Lunghezza selezionare Esattamente e specificare **0** in **Cifre** da rimuovere, l'espressione regolare risultante nel formato da cercare **corrisponderà** alla seguente:

    **^(\d {7} )$**

7. In **Regola di conversione** specificare un modello per il formato dei numeri di telefono E.164 convertiti, come indicato di seguito:
    - Un valore che rappresenta il numero di cifri specificato nel formato della corrispondenza. Ad esempio, se il criterio di corrispondenza è **^(\d {7} )$**, $1 nella regola di conversione rappresenta i numeri composto a 7 cifre.
    - (Facoltativo) Digitare un valore nel campo **Prefisso** per specificare le cifre da anteporre al numero convertito (ad esempio **+1425**).
    
    Ad esempio, se **pattern da** abbinare contiene **^(\d {7} )$** come modello per i numeri composto e la regola di conversione contiene **+1425$1** come modello per i numeri di telefono E.164, la regola normalizza da 5550100 a +14255550100. 

8. (Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.
9. (Facoltativo) Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.
    > [!Note] 
    > È possibile salvare una regola di normalizzazione che non passa ancora il test e quindi riconfigurarla successivamente. Per informazioni dettagliate, vedere [Test voice routing.](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx) 

10. Fare clic su **OK** per salvare la regola di normalizzazione.
11. Fare clic su **OK** per salvare il dial plan.
12. Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**. 
    > [!Note]
    > Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando Salva tutto per pubblicare la modifica apportata alla configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration.](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx) 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Creare o modificare manualmente una regola di normalizzazione

Completare la procedura seguente se si desidera creare o modificare manualmente una regola di normalizzazione.

**Per definire manualmente una regola di normalizzazione**

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [Delegare le autorizzazioni di installazione.](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo. Per informazioni dettagliate sui diversi metodi che puoi usare per avviare il Pannello di controllo di Skype for Business, vedi [Installare e aprire gli strumenti di amministrazione.](../../management-tools/install-and-open-administrative-tools.md)
3. (Facoltativo) Seguire i passaggi descritti in [Creare un dial plan](GET LINK AFTER MIGRATION) fino al passaggio 11 o modificare un dial plan fino [al](GET LINK AFTER MIGRATION) passaggio 10.  
4. In Nuova regola  **di normalizzazione** o Modifica regola di normalizzazione digitare un nome che descriva il modello di numero normalizzato in **Nome** (ad esempio, assegnare alla regola di normalizzazione il nome **5DigitExtension).**
5. (Facoltativo) In **Descrizione** digitare una descrizione della regola di normalizzazione, ad esempio "Converte prefissi a 5 cifre".
6. In **Crea regola di normalizzazione fare** clic su **Modifica.**
7. Immettere quanto segue in Digita espressione regolare:
    - In **Corrispondenza a questo modello** specificare il formato che si desidera utilizzare per la corrispondenza con il numero di telefono composto.
    - In **Regola di conversione** specificare un formato per il formato dei numeri di telefono E.164 convertiti.

    Ad esempio, se si immette **^(\d {7} )$** in Corrispondenza a questo **modello** e **+1425$1** **nella** regola di conversione, la regola normalizza da 5550100 a +14255550100.

8. (Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.
9. (Facoltativo) Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.

    > [!Note]
    > È possibile salvare una regola di normalizzazione che non passa ancora il test e quindi riconfigurarla successivamente. Per informazioni dettagliate, vedere [Test voice routing.](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx) 

10. Fare clic su **OK** per salvare la regola di normalizzazione.
11. Fare clic su **OK** per salvare il dial plan.
12. Nella pagina **Dial plan** fare clic su **Commi** t e quindi su **Commit tutto.** 
