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
description: "Se è necessario rimuovere il file server che funge attualmente da archivio file per la distribuzione di Skype for Business Server o se è necessario apportare altre modifiche che renderebbero l'archivio file corrente non disponibile, è innanzitutto necessario creare una nuova condivisione. È quindi necessario eseguire la procedura seguente:"
ms.openlocfilehash: 6121083d736075fa9ec58380dbc09ef6a8c4ef68
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819606"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>Spostare i dati dell'archivio file in un nuovo archivio file in Skype for Business Server

Se è necessario rimuovere il file server che funge attualmente da archivio file per la distribuzione di Skype for Business Server o se è necessario apportare altre modifiche che renderebbero l'archivio file corrente non disponibile, è innanzitutto necessario creare una nuova condivisione. È quindi necessario eseguire la procedura seguente:

1. Arrestare i servizi di Skype for Business Server che utilizzano l'archivio file che si intende rimuovere.

2. Definire l'archivio file in Generatore di topologie e pubblicare le modifiche per rendere disponibile il nuovo archivio file per la distribuzione.

3. Spostare i dati nel nuovo archivio file.

4. Riavviare i server o i servizi.

5. Facoltativamente, rimuovere la condivisione file e la cartella file precedente.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Per spostare i dati dell'archivio file in un nuovo archivio

1. Accedere a un computer come membro del gruppo RTCUniversersalServerAdmins o CsServerAdministrator in cui è installato Skype for Business Server, Strumenti di amministrazione.

2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.

3. Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.

4. Per ogni pool di server Director, Director, server Standard Edition e pool Front End che utilizza l'archivio file che si intende rimuovere, selezionare il server o il pool, fare clic su Azione e quindi su Arresta tutti i **servizi.**

5. Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

6. Avviare Generatore di topologie: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server** e quindi Generatore di topologie di Skype for Business **Server.**

7. Selezionare un server o un pool che utilizza l'archivio file ed eseguire le operazioni seguenti:

8. Fare clic con il pulsante destro del mouse sul server o sul pool e **quindi scegliere Modifica proprietà.**

9. In **Modifica proprietà,** in **Associazioni,** in **Archivio file,** fare clic su **Nuovo.**

10. In **Definisci nuovo archivio file,** in FQDN file **server,** digitare il nome di dominio completo (FQDN) del file server. In **Condivisione file** digitare il nome della nuova condivisione file e quindi fare clic su **OK.**

     > [!IMPORTANT]
     > In questo passaggio viene definito un nuovo archivio file da utilizzare in Generatore di topologie. È possibile definirla una sola volta, non per ogni server. Prima di pubblicare la topologia è necessario creare l'archivio file definito nel file server definito. Per informazioni dettagliate, vedere [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

11. Per ogni server o pool che utilizza l'archivio file, eseguire le operazioni seguenti:

12. Fare clic con il pulsante destro del mouse sul server o sul pool e **quindi scegliere Modifica proprietà.**

13. In **Modifica proprietà,** in **Associazioni,** nell'archivio **file,** selezionare la nuova condivisione file e quindi fare clic su **OK.**

14. Pubblicare la topologia, controllare lo stato della replica ed eseguire la Distribuzione guidata di Skype for Business Server in base alle esigenze. Per informazioni dettagliate, vedere [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

15. Avviare un prompt dei comandi: fare clic sul **pulsante Start,** scegliere **Esegui** e quindi digitare cmd.exe.

16. Nella riga di comando digitare quanto segue:

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > L'opzione /S copia file, directory e sottodirectory. L'opzione /XF ignora tutti i file denominati Meeting.Active. Le versioni correnti di robocopy.exe con il parametro /MT offrono una velocità di copia notevolmente superiore grazie all'utilizzo di più thread. Per l'opzione /LOG, utilizzare un percorso di directory e un nome di file di registro nel formato C:\Logfiles\log.txt. Questa opzione consente di creare un file di registro delle operazioni nel percorso specificato.

17. Al termine della copia dei dati, nel Pannello di controllo di Lync Server fare clic su **Topologia** e quindi su **Stato.**

18. Per ogni server o pool in cui sono stati arrestati i servizi, selezionare il server o il pool, fare clic su **Azione** e quindi su **Avvia tutti i servizi.**

19. Rimuovere il vecchio archivio file dalla topologia e quindi pubblicare la topologia. Per informazioni dettagliate, vedere [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

20. (Facoltativo) Accedere al computer che contiene l'archivio file appena rimosso come membro del gruppo Administrators locale o del gruppo Domain Admins, quindi rimuovere la vecchia condivisione file e la vecchia directory.

## <a name="see-also"></a>Vedere anche

[Riassegnare un server a un archivio file diverso](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Rimuovere un archivio file](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
