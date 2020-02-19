---
title: 'Lync Server 2013: assegnare un criterio di chat persistente per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e06d6c7403bd348b44c6ab36216ed7ee9a1c6d02
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134412"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a>Assegnazione di criteri di chat persistente per utente in Lync Server 2013

 


È possibile assegnare criteri di chat persistente per utente con il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell. Per informazioni dettagliate sulla creazione di criteri utente per il server Chat persistente, vedere [creare un criterio utente per la chat persistente in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a>Per assegnare criteri di chat persistente per utente con il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  Utilizzare uno dei metodi seguenti per individuare un utente:
    
      - Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.
    
      - Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.

5.  (Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:
    
    1.  Fare clic su **Aggiungi filtro**.
    
    2.  Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.
    
    3.  Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).
    
    4.  A seconda della proprietà utente selezionata, immettere i criteri da utilizzare per filtrare i risultati della ricerca digitandoli o facendo clic sulla freccia dell'elenco a discesa.
        

        > [!TIP]  
        > Per aggiungere ulteriori clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.

    
    5.  Fare clic su **Trova**.

6.  Fare clic su un utente nei risultati di ricerca, fare clic su **Azione** e quindi fare clic su **Assegna criteri**.
    

    > [!TIP]  
    > Se si desidera applicare gli stessi criteri di chat persistente a più utenti, selezionare più utenti all'interno dei risultati di ricerca, fare clic su <STRONG>Azioni</STRONG> e quindi su <STRONG>Assegna criteri</STRONG>.



7.  In **Assegna criteri** eseguire una delle operazioni seguenti in **Criteri chat persistente**:
    

    > [!NOTE]  
    > Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt;Mantieni come è&gt; </STRONG> selezionato per impostazione predefinita per tutti i criteri nella finestra di dialogo. Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.

    
      - Selezionare ** \<automatico\> ** per consentire a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.
    
      - Fare clic sul nome dei criteri di chat persistente per utente precedentemente definiti nella pagina **Criteri chat persistente**.
        

        > [!TIP]  
        > Per decidere quali criteri assegnare, dopo aver selezionato un nome di criteri, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definite nei criteri.



8.  Al termine, fare clic su **OK**.

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a>Assegnazione di criteri di chat persistente per utente tramite i cmdlet di Windows PowerShell

È inoltre possibile assegnare criteri di chat persistente per utente utilizzando il cmdlet **Grant-CsPersistentChatPolicy** . È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a>Per assegnare criteri di chat persistente per utente a un singolo utente

  - Il comando seguente consente di assegnare i criteri di chat persistente per utente denominati RedmondPersistentChatPolicy all'utente Ken Myer.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a>Per assegnare criteri di chat persistente per utente a più utenti

  - Questo comando consente di assegnare i criteri di chat persistente per utente RedmondUsersPersistentChatPolicy a tutti gli utenti che fanno parte del reparto IT. Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a>Per annullare l'assegnazione di un criterio di chat persistente per utente

  - Il comando seguente consente di annullare l'assegnazione dei criteri di chat persistente per utente precedentemente assegnati all'utente Ken Myer. Dopo l'annullamento dell'assegnazione dei criteri per utente, Ken Myer verrà gestito automaticamente tramite i criteri globali oppure i criteri di sito locale, se esistenti. I criteri di sito sono prioritari rispetto ai criteri globali.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) .

## <a name="see-also"></a>Vedere anche


[Creare un criterio utente per la chat persistente in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

