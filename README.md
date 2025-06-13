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

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

import 'dart:html';
import 'dart:io';

import 'package:flutter/material.dart';
import 'package:flutter/services.dart';
import 'Cast.dart';
import 'Info.dart';
import 'gallery.dart';

void main() {
  runApp(MaterialApp(
    title: "App",
    home: MainApp(),
  ));
}

class MainApp extends StatelessWidget {
  MainApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        backgroundColor: const Color.fromRGBO(214, 114, 40, 1),

        appBar: AppBar(
          backgroundColor: const Color.fromRGBO(214, 114, 40, 1),
          centerTitle: true,
          title: const Text(
              style: TextStyle(
                fontWeight: FontWeight.bold,
                fontSize: 40,
                fontStyle: FontStyle.italic,
                color: Color.fromRGBO(82, 15, 15, 1),
              ),
              'TOMB RAIDER'),
        ),

        bottomNavigationBar: BottomAppBar(
          color: Colors.black,
          child: Row(
            children: [
              SizedBox(
                width: 10,
              ),
              IconButton(
                onPressed: () {
                  SystemNavigator.pop();
                }, //exit(0),
                icon: Icon(Icons.exit_to_app, color: Colors.white),
              ),
              SizedBox(
                width: 120,
              ),
              IconButton(
                onPressed: (null),
                icon: Icon(Icons.apartment, color: Color(0xff14ddff)),
              ),
              Text(
                style: TextStyle(color: Colors.white),
                "Crystal Dynamics",
              ),
            ],
          ),
        ),

        //bottomNavigationBar: const BottomAppBar(
        //  children: [IconButton(onPressed: Null, icon: Text(''))]),
        body: Center(
            child: Column(children: <Widget>[
          Column(mainAxisAlignment: MainAxisAlignment.center, children: [
            Text(
                style: TextStyle(
                  fontWeight: FontWeight.bold,
                  fontSize: 30,
                  color: Colors.black,
                ),
                "RESUMO"),

            // Separaçao Título do Texto - Texto

            SizedBox(
              width: 240,
              child: Text(
                  textAlign: TextAlign.justify,
                  style: TextStyle(
                    fontSize: 19,
                    color: Colors.black,
                  ),
                  " No reboot Tomb Raider (2013), você joga com a jovem Lara Croft, numa expedição para encontrar uma ilha misteriosa chamada Yamatai. Após um naufrágio, Lara precisa sobreviver a perigos mortais, enfrentar cultistas, e descobrir segredos antigos para salvar seus amigos."),
            ),

            SizedBox(
              height: 30,
            ),

            SizedBox(
              width: 100,
              height: 50,
              child: FloatingActionButton(
                  onPressed: () {
                    Navigator.push(context,
                        MaterialPageRoute(builder: (context) => Info()));
                  },
                  backgroundColor: Color(0xff000000),
                  child: Text(
                      style: TextStyle(
                        color: Color(0xffffffff),
                      ),
                      "Sobre o Jogo")),
            ),
          ]),
          Row(
            mainAxisAlignment: MainAxisAlignment.spaceBetween,
            children: [
              SizedBox(
                width: 100,
                height: 50,
                child: FloatingActionButton(
                    onPressed: () {
                      Navigator.push(context,
                          MaterialPageRoute(builder: (context) => Cast()));
                    },
                    backgroundColor: Color(0xff000000),
                    child: Text(
                        style: TextStyle(
                          color: Colors.white,
                        ),
                        "Elenco")),
              ),
              SizedBox(
                width: 100,
                height: 50,
                child: FloatingActionButton(
                    onPressed: () {
                      Navigator.push(context,
                          MaterialPageRoute(builder: (context) => Gallery()));
                    },
                    backgroundColor: Color(0xff000000),
                    child: Text(
                        style: TextStyle(
                          color: Colors.white,
                        ),
                        "Galeria")),
              ),
            ],
          )
        ])),
      ),
    );
  }
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

import 'dart:ui';
import 'package:flutter/material.dart';
import 'Arrays.dart';

class Info extends StatelessWidget {
  Info({super.key});
  @override
  Widget build(BuildContext context) {
    return Scaffold(
        backgroundColor: const Color.fromRGBO(214, 114, 40, 1),
        appBar: AppBar(
          backgroundColor: const Color.fromRGBO(214, 114, 40, 1),
          centerTitle: true,
          title: const Text(
            'TOMB RAIDER',
            style: TextStyle(
              fontWeight: FontWeight.bold,
              fontSize: 30,
              fontStyle: FontStyle.italic,
              color: Color.fromRGBO(82, 15, 15, 1),
            ),
          ),
        ),
        bottomNavigationBar: BottomAppBar(
          color: Colors.black,
          child: Row(
            children: [
              SizedBox(
                width: 10,
              ),
              IconButton(
                onPressed: () {
                  Navigator.pop(context);
                },
                icon: Icon(Icons.home, color: Color(0xffffffff)),
              ),
              SizedBox(
                width: 140,
              ),
              Icon(Icons.apartment, color: Color(0xff14ddff)),
              Text(
                style: TextStyle(color: Colors.white),
                "Crystal Dynamics",
              ),
            ],
          ),
        ),
        body: PageView.builder(
            itemCount: info.length,
            pageSnapping: true,
            itemBuilder: (context, valor) {
              return Container();
            }));
  }
}

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


import 'package:flutter/material.dart';
import 'Arrays.dart';

class Gallery extends StatelessWidget {
  Gallery({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: const Color.fromRGBO(214, 114, 40, 1),
      appBar: AppBar(
        backgroundColor: const Color.fromRGBO(214, 114, 40, 1),
        centerTitle: true,
        title: const Text(
          'TombRaider',
          style: TextStyle(
            fontWeight: FontWeight.bold,
            fontSize: 30,
            color: Color.fromRGBO(82, 15, 15, 1),
          ),
        ),
      ),
      bottomNavigationBar: BottomAppBar(
        color: Colors.black,
        child: Row(
          children: [
            SizedBox(
              width: 10,
            ),
            IconButton(
              onPressed: () {
                Navigator.pop(context);
              },
              icon: Icon(Icons.home, color: Color(0xffffffff)),
            ),
            SizedBox(
              width: 140,
            ),
            Icon(Icons.apartment, color: Color(0xff14ddff)),
            Text(
              style: TextStyle(color: Colors.white),
              "Crystal Dynamics",
            ),
          ],
        ),
      ),
      body: Center(
        child: SizedBox(
          width: double.infinity,
          height: 200,
          child: PageView.builder(
              scrollDirection: Axis.horizontal,
              itemCount: galleryphotos.length,
              itemBuilder: (context, index) {
                return Container(
                  margin: const EdgeInsets.symmetric(horizontal: 10),
                  decoration: BoxDecoration(
                      borderRadius: BorderRadius.circular(10),
                      image: DecorationImage(
                          image: NetworkImage(galleryphotos[index]))),
                );
              }),
        ),
      ),
    );
  }
}


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


import 'dart:math';
import 'dart:ui';
import 'package:sadsad/Arrays.dart';
import 'Arrays.dart';

import 'package:flutter/material.dart';

class Cast extends StatelessWidget {
  Cast({super.key});
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: const Color.fromRGBO(214, 114, 40, 1),
      appBar: AppBar(
        backgroundColor: const Color.fromRGBO(214, 114, 40, 1),
        centerTitle: true,
        title: const Text(
          'ELENCO TOMB RAIDER',
          style: TextStyle(
            fontWeight: FontWeight.bold,
            fontSize: 25,
            fontStyle: FontStyle.italic,
            color: Color.fromRGBO(82, 15, 15, 1),
          ),
        ),
      ),
      bottomNavigationBar: BottomAppBar(
        color: Colors.black,
        child: Row(
          children: [
            SizedBox(
              width: 10,
            ),
            IconButton(
              onPressed: () {
                Navigator.pop(context);
              },
              icon: Icon(Icons.home, color: Color(0xffffffff)),
            ),
            SizedBox(
              width: 140,
            ),
            Icon(Icons.apartment, color: Color(0xff14ddff)),
            Text(
              style: TextStyle(color: Colors.white),
              "Crystal Dynamics",
            ),
          ],
        ),
      ),
      body: ListView.builder(
          itemCount: atores.length,
          itemBuilder: (BuildContext context, int index) {
            return ListTile(
              leading: CircleAvatar(
                  //    backgroundImage: Image.network(imagens_atores[index])), -> Codigo errado por conta do Image.network invés do NetworkImage.
                  backgroundImage: NetworkImage(imagensatores[index])),
              title: Text(
                  style: TextStyle(
                      fontSize: 20,
                      fontWeight: FontWeight.bold,
                      color: Colors.black),
                  atores[index].actorname),
              subtitle: Text(
                  style: TextStyle(fontSize: 14, color: Colors.black),
                  atores[index].personame),
            );
          }),
    );
  }
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

import 'package:flutter/material.dart';

class Actor {
  final String actorname;
  final String personame;

  Actor(
    this.actorname,
    this.personame,
  );
}

List atores = [
  Actor("Lara Croft", "Camilla Luddington"),
  Actor("Conrad Roth", "Robin Atkin Downes"),
  Actor("Mathias", "Richard Dillane"),
  Actor("Sam Nishimura", "Gillian Anderson"),
  Actor("Jonah Maiava", "Ralph Ineson"),
];

List<String> imagensatores = [
  "https://vignette.wikia.nocookie.net/dcmovies/images/5/55/Camilla_Luddington.jpg/revision/latest/scale-to-width-down/2000?cb=20160726182959",
  "https://vignette.wikia.nocookie.net/the-owl-house/images/a/aa/Robin_Atkin_Downes_Pic.jpg/revision/latest?cb=20200712190725",
  "https://www.themoviedb.org/t/p/w600_and_h900_bestv2/4DVdlTFkhPlERFyFoeH6UoXb2un.jpg",
  "http://images5.fanpop.com/image/photos/32000000/Gillian-gillian-anderson-32062066-1024-768.jpg",
  "https://media1.popsugar-assets.com/files/thumbor/eVWiqq24BiAS6wwuFX_oOMgh8i4/fit-in/1024x1024/filters:format_auto-!!-:strip_icc-!!-/2018/12/17/091/n/1922283/0cbcd80f02a6c491_GettyImages-1031169276/i/Ralph-Ineson.jpg",
];

//List<String> galeria = [
// ("http://hdqwalls.com/wallpapers/tomb-raider-2015.jpg"),
// ("https://tse3.mm.bing.net/th?id=OIP.JjFJKbaSyC7erAg0KP9MpgHaEe&pid=Api&P=0&h=180"),
//("https://tse3.mm.bing.net/th?id=OIP.D5PApcD4nEW_kdnnT_To9gHaEK&pid=Api&P=0&h=180"),
//];

/* class Informacao {
  final String titulo;
  final String descricao;
  final String links;

  Informacao(
    this.titulo,
    this.descricao,
    this.links,
  );
}

List textos = [
  Informacao("T", "S", "F"),
  Informacao("T", "S", "F"),
  Informacao("T", "S", "F"),
]; */

List<String> galleryphotos = [
  "https://media.themoviedb.org/t/p/w500/sn3ONJw2pJxMHiCqPwvkaiWr5mc.jpg",
  "https://assets.mycast.io/actor_images/actor-ralph-ineson-354948_large.jpg?1643529532",
];

List<Widget> info = [
  Container(
    child: Row(
      children: [
        Text(style: TextStyle(), 'SOBRE O JOGO'),
        Text(style: TextStyle(), 'SubTitle'),
        Text(style: TextStyle(), 'Content'),
        Text(style: TextStyle(), 'SubTitle'),
        Text(style: TextStyle(), 'Content'),
        Text(style: TextStyle(), 'SubTitle'),
        Text(style: TextStyle(), 'Content'),
      ],
    ),
  ),
  Container(
    child: Row(
      children: [
        Text(style: TextStyle(), 'DADOS DE LANÇAMENTO'),
        Text(style: TextStyle(), 'SubTitle'),
        Text(style: TextStyle(), 'Content'),
        Text(style: TextStyle(), 'SubTitle'),
        Text(style: TextStyle(), 'Content'),
        Text(style: TextStyle(), 'SubTitle'),
        Text(style: TextStyle(), 'Content'),
      ],
    ),
  ),
  Container(
    child: Row(
      children: [
        Text(style: TextStyle(), 'MÍDIA'),
        Text(style: TextStyle(), 'SubTitle'),
        Text(style: TextStyle(), 'Content'),
        Text(style: TextStyle(), 'SubTitle'),
        Text(style: TextStyle(), 'Content'),
        Text(style: TextStyle(), 'SubTitle'),
        Text(style: TextStyle(), 'Content'),
      ],
    ),
  ),
];
