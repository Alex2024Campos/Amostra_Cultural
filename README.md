>[!Important]
> ` - Projeto:`
>- Turma: 3°Mtec Desenvolvimento de Jogos Digitais.
>- Escola: Etec Prof. Basilides de Godoy.
>- Sobre: Repositório com o propósito de armazenar nosso levantamento de dados, arquivos relacionados à pesquisa e o projeto para a feira cultural do 3°MTEC em Desenvolvimento de Jogos Digitais e da Etec Prof. Basilides de Godoy.
>
> ` - Equipe:`
>- Alex Campos de Oliveira
>- Felipe Mussato Rodrigues
>- Guilherme Henrique
>- Kauan Merida
>

> [!NOTE]
 > ` - Avisos:`
 > Esse setor da documentação terá a função de conter qualquer aviso ou anúncio sobre o nosso jogo e sua documentação.

https://assetstore.unity.com/packages/3d/environments/historic/low-poly-game-ready-history-village-207553

https://assetstore.unity.com/packages/3d/environments/fantasy/low-poly-fantasy-medieval-village-vol-2-lite-242322

https://assetstore.unity.com/packages/3d/environments/abandoned-buildings-62875

https://sketchfab.com/3d-models/the-ramey-house-8c467e9a644d46988323fe199470dcba

https://sketchfab.com/3d-models/house-test-8ccdacecef714a4bb1e7eaa7075695c7

https://sketchfab.com/3d-models/building-container-metal-36380c606bae46848237e9bbe073fa3b

https://sketchfab.com/3d-models/painted-house-zalipie-in-southern-poland-2b7c7d770cf1406fb0c9f19873675008

https://sketchfab.com/3d-models/old-garage-79a1901fe45d4891a87596b79de057ae

https://sketchfab.com/3d-models/house-farm-wood-13-mb-a9732b6c1c4249a08477de9fc53ee6ad

https://sketchfab.com/3d-models/old-house-77324271ad6248468b17d3c41bb28b26

https://assetstore.unity.com/publishers/50313

https://assetstore.unity.com/packages/3d/props/rope-tool-200856

![image](https://github.com/user-attachments/assets/a6d8fbbc-744a-4779-92b2-5d14bc3c1233)


https://lucid.app/lucidchart/a7e6b56a-dd2e-47b6-91de-6ead33ebe72f/edit?viewport_loc=-1800%2C-1525%2C4010%2C1946%2CHWEp-vi-RSFO&invitationId=inv_dc7244d2-b47e-4b05-a378-fb2bab6301a6


using NUnit.Framework.Constraints;
using UnityEditor.Rendering;
using UnityEngine;
using TMPro;

public class NPC : MonoBehaviour
{
    public int I;
    public string[] DialogText;
    public TMP_Text ActualDialog;
    private Vector3 Rotate;
    void Start()
    {
        I = 0;
    }

    // Update is called once per frame
    void Update()
    {

    }

    public void Dialog()
    {
        if (Input.GetKey(KeyCode.Space))
        {
            ActualDialog.text = DialogText[I];
            I++;
        }
    }
}


using UnityEngine;
using TMPro;
using UnityEngine.UI;

public class UI : MonoBehaviour
{
    public string[] Objective;
    private TMP_Text ActualObjective;
    private TMP_Text ConsumibleValor;

    public Slider HPBar;
    public float Maxlife;
    public float ActualLife;


    void Start()
    {
        Maxlife = HPBar.maxValue;
        ActualLife = Maxlife;

    }

    // Update is called once per frame
    void Update()
    {
        if (Input.GetKey(KeyCode.Space)) {
            ActualLife -= 10;
        }
        HPBar.value = ActualLife;
    }

}

using System.Drawing;
using Unity.VisualScripting;
using UnityEngine;

public class Player : MonoBehaviour
{
    public Collision x;
    public UI ui;

    public float Life;
    public float Damage;
    private float Range;

    private bool IsAttacking;
    public bool Spotted;
    private string InteractText;
    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        Life = ui.Maxlife;
        IsAttacking = false;
        Spotted = false;


    }

    // Update is called once per frame
    void Update()
    {

    }


    private void Attack()
    {
        if (Input.GetKey(KeyCode.Mouse0)) {
            IsAttacking = true;

        }
    }

    private void Interaction()
    {
    }


}

using UnityEngine;
using TMPro;
using UnityEngine.UI;
using UnityEngine.SceneManagement;

public class UI : MonoBehaviour
{
    public int I;
    public string[] Objective;
    private TMP_Text ActualObjective;
    private TMP_Text ConsumibleValor;

    public Slider HPBar;
    public float Maxlife;
    public float ActualLife;

    private bool Scenepassed;

    void Start()
    {
        I = 0;
        Maxlife = HPBar.maxValue;
        ActualLife = Maxlife;

    }

    // Update is called once per frame
    void Update()
    {
        if (Input.GetKey(KeyCode.Space)) {
            ActualLife -= 10;
        }
        HPBar.value = ActualLife;
    }

    private void SwitchObjective()
    { 
            if(Scenepassed = true)
        {
            ActualObjective.text = Objective[I];
            I++;
        }

    }
}

