---
title: Spostare i dati dell'archivio file in un nuovo archivio file in Skype for Business Server
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
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: "Se è necessario rimuovere il file server che attualmente funge da archivio file per la distribuzione di Skype for Business Server o se è necessario apportare altre modifiche che renderebbero l'archivio file corrente non disponibile, è innanzitutto necessario creare una nuova condivisione. È quindi necessario eseguire la procedura seguente:"
ms.openlocfilehash: 4e9a28fa1793e642fbf3407c6a6306a979fa287844a9862a55780f1bd1169f82
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342481"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>Spostare i dati dell'archivio file in un nuovo archivio file in Skype for Business Server

Se è necessario rimuovere il file server che attualmente funge da archivio file per la distribuzione di Skype for Business Server o se è necessario apportare altre modifiche che renderebbero l'archivio file corrente non disponibile, è innanzitutto necessario creare una nuova condivisione. È quindi necessario eseguire la procedura seguente:

1. Arrestare i Skype for Business Server che utilizzano l'archivio file che si intende rimuovere.

2. Definire l'archivio file in Generatore di topologie e pubblicare le modifiche per rendere disponibile il nuovo archivio file per la distribuzione.

3. Spostare i dati nel nuovo archivio file.

4. Riavviare i server o i servizi.

5. Facoltativamente, rimuovere la condivisione file e la cartella di file precedente.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Per spostare i dati dell'archivio file in un nuovo archivio

1. Accedere a un computer come membro del gruppo RTCUniversersalServerAdmins o CsServerAdministrator in cui è installato Skype for Business Server strumenti di amministrazione.

2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.

3. Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.

4. Per ogni pool di server Director, Server Director, server edizione Standard e pool Front End che utilizza l'archivio file che si intende rimuovere, selezionare il server o il pool, fare clic su Azione e quindi su Arresta tutti i **servizi.** 

5. Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

6. Avviare Generatore di topologie: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server** e quindi fare clic Skype for Business Server Generatore **di topologie.**

7. Selezionare un server o un pool che utilizza l'archivio file ed eseguire le operazioni seguenti:

8. Fare clic con il pulsante destro del mouse sul server o sul pool e **quindi scegliere Modifica proprietà**.

9. In **Modifica proprietà,** in **Associazioni,** in **Archivio file** fare clic su **Nuovo.**

10. In **Definisci nuovo archivio file** digitare il nome di dominio completo (FQDN) del file server in **FQDN** file server. In **Condivisione file** digitare il nome della cartella per la nuova condivisione file e quindi fare clic su **OK.**

     > [!IMPORTANT]
     > In questo passaggio viene definito un nuovo archivio file da utilizzare in Generatore di topologie. È possibile definirlo una sola volta, non per ogni server. Prima di pubblicare la topologia è necessario creare l'archivio file definito nel file server definito. Per informazioni dettagliate, vedere [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).

11. Per ogni server o pool che utilizza l'archivio file, eseguire le operazioni seguenti:

12. Fare clic con il pulsante destro del mouse sul server o sul pool e **quindi scegliere Modifica proprietà**.

13. In **Modifica proprietà,** in **Associazioni,** in **Archivio file,** selezionare la nuova condivisione file e quindi fare clic su **OK.**

14. Pubblicare la topologia, controllare lo stato della replica ed eseguire la Skype for Business Server distribuzione guidata in base alle esigenze. Per informazioni dettagliate, vedere [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).

15. Avviare un prompt dei comandi: fare clic sul **pulsante Start,** scegliere **Esegui** e quindi digitare cmd.exe.

16. Nella riga di comando digitare quanto segue:

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > L'opzione /S consente di copiare file, directory e sottodirectory. L'opzione /XF ignora tutti i file denominati Meeting.Active. Le versioni correnti di robocopy.exe con il parametro /MT offrono una velocità di copia notevolmente superiore grazie all'utilizzo di più thread. Per l'opzione /LOG, utilizzare un percorso di directory e un nome di file di registro sotto forma di C:\Logfiles\log.txt. Questa opzione consente di creare un file di registro delle operazioni nel percorso specificato.

17. Al termine della copia dei dati, nel Pannello di controllo di Lync Server fare clic su **Topologia** e quindi su **Stato.**

18. Per ogni server o pool in cui sono stati arrestati i servizi, selezionare il server o il pool, fare clic su **Azione** e quindi su **Avvia tutti i servizi.**

19. Rimuovere il vecchio archivio file dalla topologia e quindi pubblicare la topologia. Per informazioni dettagliate, vedere [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).

20. (Facoltativo) Accedere al computer che contiene l'archivio file appena rimosso come membro del gruppo Administrators locale o del gruppo Domain Admins, quindi rimuovere la vecchia condivisione file e la vecchia directory.

## <a name="see-also"></a>Vedere anche

[Riassegnare un server a un archivio file diverso](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))

[Rimuovere un archivio file](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))