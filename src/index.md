---
marp: true
paginate: true
backgroundSize: auto
theme: default
style: | 
  .cls { 
      display: grid; 
      grid-template-columns: 
      repeat(2, minmax(0, 1fr)); 
      gap: 1rem; 
  }
---


![bg left](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=O)
![bg](https://fakeimg.pl/800x600/246/fff/?text=L)
![bg](https://fakeimg.pl/800x600/246/fff/?text=I)
![bg](https://fakeimg.pl/800x600/246/fff/?text=D)


## Uma introdução ao conjunto de princípios fundamentais para 
# O desenvolvimento de software saudável

---

## Princípios solidos

<!-- 

Bons sistemas começam com pequenos pedaços de código limpo. Por outro lado, é possível fazer uma bagunça considerável com vários pequenos pedaços de código limpo. É aí que entram os princípios SOLID.
-->

--- 

## Princípios sólidos
# Organização

<!-- 

  Os principios SOLID nos dizem como organizar as funções e estruturas de dados em classes e como essas classes devem ser interconectadas.

-->


--- 

<div class="cls">
  <div>

  ## Objetivos do 
  # SOLID <!-- fit -->

  </div>
  <div style="padding: 100px 100px 0 0;">

  - Tolerar mudanças
  - Sejam faceis de entender
  - Sejam a base de código que possa ser usada em muitos sistemas de software

  </div>
</div>


<!-- 

Assim como é possivel criar uma bagunça considerável com tijolos bem feitos, 
também é possível bagunçar um sistema inteiro com pedaços de código bem-projetados.

-->

--- 

![bg vertical left:33%](https://fakeimg.pl/800x600/0288d1/fff/?text=Breve)
![bg](https://fakeimg.pl/800x600/fff/0288d1/?text=história)



# SOLID <!-- fit --> 

--- 

![bg](https://cleancoders.com/images/portraits/robert-martin.jpg)
![bg vertical left:33%](https://media.licdn.com/dms/image/v2/D4E22AQEXAc7ytxDZjA/feedshare-shrink_800/feedshare-shrink_800/0/1709807964294?e=2147483647&v=beta&t=AlA8xwr73NqK7cpYfRmMEBYxCi_0rdawSMS9VTLjJBg)

    
Robert C Martin (signatário do Manifesto Agil, autor do da série de livros codigo limpo e  desenvolvedor desde a década de 70), vem escrevendo sobre qualidade de software a muito tempo e em 2000 já havia estabelecido um conjunto de princípios e práticas em seus trabalhos e publicações. 

Foi ai que em 2004, Michael Feathers (um importante e antigo desenvolvedor da comunidade C++) percebeu que se reorganizasse os princípios, as primeiras letras de cada principio poderiam formar a palavra SOLID.

Assim nasceu os princípios SOLID.

---

![bg left](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=O)
![bg](https://fakeimg.pl/800x600/246/fff/?text=L)
![bg](https://fakeimg.pl/800x600/246/fff/?text=I)
![bg](https://fakeimg.pl/800x600/246/fff/?text=D)

---

![bg left](https://fakeimg.pl/800x600/246/fff/?text=S&font=lobster)
![bg](https://fakeimg.pl/800x600/246,120/?text=O)
![bg](https://fakeimg.pl/800x600/246,120/?text=L)
![bg](https://fakeimg.pl/800x600/246,120/?text=I)
![bg](https://fakeimg.pl/800x600/246,120/?text=D)

# Single <!-- fit -->
# Responsability <!-- fit -->
# Principle <!-- 1fit -->

---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=R)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)


# Principio <!-- 1fit -->
## Responsabilidade <!-- fit -->
# Unica <!-- 1fit -->

---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=R)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)


<div class="cls">
<div style="padding-top: 40%">

``` java

public class Robot {
  void cook() { ... }
  void text() { ... }
  void state() { ... }
  void image() { ... }
  void video() { ... }
  void youtube() { ... }
}
```

</div>
<div >

![](./images/srp1.1.png)

</div>
</div>

---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=R)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)


<div class="cls">
<div >

![](./images/srp1.2.png)

</div>
<div>

``` java

public class RobotChef {
  void cook() { ... }
}

public class RobotGarderner {
  void clean() { ... }
}

public class RobotPainter {
  void paint() { ... }
}

public class RobotDriver {
  void drive() { ... }
}

```


</div>
</div>

---

![bg left](https://fakeimg.pl/800x600/246,120/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=O&font=lobster)
![bg](https://fakeimg.pl/800x600/246,120/?text=L)
![bg](https://fakeimg.pl/800x600/246,120/?text=I)
![bg](https://fakeimg.pl/800x600/246,120/?text=D)


# Open-Closed <!-- fit -->
# Principle <!-- 1fit -->

---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=O)
![bg](https://fakeimg.pl/800x600/246/fff/?text=C)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)

# Princípio <!-- 1fit -->
# Aberto-Fechado <!-- fit -->


---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=O)
![bg](https://fakeimg.pl/800x600/246/fff/?text=C)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)


<div class="cls">
<div style="padding-top: 10%">

``` java

public class Robot {
  void exec() { 
    this.skill.cut();
   }
}

// ⬇️

public class Robot {
  void exec() { 
    this.skill.paint();
   }
}

```

</div>
<div >

![](./images/ocp1.1.png)

</div>
</div>


---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=O)
![bg](https://fakeimg.pl/800x600/246/fff/?text=C)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)


<div class="cls">
<div style="padding-top: 10%">

![](./images/ocp1.2.png)

</div>
<div >

``` java

public class Robot {
  
  Robot(Array<Skil>l skills){ 
    this.skills = skills;
  }
  
  void exec() { 
    for (Skill skill: this.skills){
      skill.exec();
    }
   }
}


```

</div>
</div>

<!-- 
Não precisamos alterar o codigo do Robot para modificar seu comportamento
-->

---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=O)
![bg](https://fakeimg.pl/800x600/246/fff/?text=C)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)


<div class="cls">
<div style="padding-top: 10%">

![](./images/ocp1.2.png)

</div>
<div >

``` java

public class CookSkill 
  implements Skill {
  
  void exec() { ... }
}

public class PaintSkill 
  implements Skill {
  
  void exec() { ... }
}
// ... more skills

// using
Robot robot = new Robot([
  new CookSkill(), 
  new PaintSkill()
]);


```

</div>
</div>

<!-- 
Agora toda vez que precisar adicionar mais um comportamento ao robô, só precisamos criar uma nova classe Skill e implementa-la!
-->

---
![bg left](https://fakeimg.pl/800x600/246,120/?text=S)
![bg](https://fakeimg.pl/800x600/246,120/?text=O)
![bg](https://fakeimg.pl/800x600/246/fff/?text=L&font=lobster)
![bg](https://fakeimg.pl/800x600/246,120/?text=I)
![bg](https://fakeimg.pl/800x600/246,120/?text=D)


# Liskov <!-- 1fit -->
# Substitution <!-- fit -->
# Principle <!-- 1fit -->

---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=L)
![bg](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)

# Princípio <!-- 1fit -->
# Substituição <!-- fit -->
# Liskov <!-- 1fit -->

---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=L)
![bg](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)

![](./images/lsp.0.png)


---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=L)
![bg](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)


<div class="cls">
<div style="padding-top: 40%">

``` java

public class Sam {
  Coffee cook() { ... }
}

public class Eden extends Sam {
  Water cook() { ... }
}

```

</div>
<div >

![](./images/lsp.1.png)

</div>
</div>

---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=L)
![bg](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)


<div class="cls">
<div>

![](./images/lsp.2.png)

</div>
<div >


``` java

public class Sam {
  Coffee cook() { ... }
}

public class Eden extends Sam {
  Coffee cook() { 
      // cappucino is a Coffee type 
      return cappucino; 
  }
}

```
</div>
</div>


---

![bg left](https://fakeimg.pl/800x600/246,120/?text=S)
![bg](https://fakeimg.pl/800x600/246,120/?text=O)
![bg](https://fakeimg.pl/800x600/246,120/?text=L)
![bg](https://fakeimg.pl/800x600/246/fff/?text=I&font=lobster)
![bg](https://fakeimg.pl/800x600/246,120/?text=D)


# Interface <!-- 1fit -->
# Segregation <!-- fit -->
# Principle <!-- 1fit -->

---


![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=I)
![bg](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)

# Princípio <!-- 1fit -->
# Segregação <!-- fit -->
# Interface <!-- 1fit -->


---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=I)
![bg](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)


``` java

public interface Robot {
  void spin(); // girar 
  void rotateArms(); // rodar braços 
  void wiggleAntenas(); // mecher antenas
}

public class Eden implements Robot {
  Pair<Arm, Arm> arms;
  Pair<Antena, Antena> antenas;


  void spin() { ... }
  void rotateArms() { ... }
  void wiggleAntenas() { ... }
}

```

---


![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=I)
![bg](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)

<div class="cls">

<div >

![](./images/isp.1.png)

</div>

<div>

``` java 

public class Sam 
  implements Robot {
  
  Pair<Arm, Arm> arms;

  void spin() { ... }
  void rotateArms() { ... }
  
  // NÃO TENHO ANTENAS
  void wiggleAntenas() { 
    throw new 
      Exception("Não tenho antenas!");
   }
}

```

</div>
</div>

---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=I)
![bg](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)

``` java 

public interface SpinRobot {
  void spin();
}

public interface ArmsRobot {
  Pair<Arm, Arm> arms;
  void rotate();
}

public interface AntenasRobot {
  Pair<Antena, Antena> antenas;
  void wiggleAntenas(); 
}

```

---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=I)
![bg](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)

<div class="cls">

<div>

``` java 
public class Eden implements 
  SpinRobot, 
  ArmsRobot, 
  AntenasRobot {
  
  Pair<Arm, Arm> arms;
  Pair<Antena, Antena> antenas;

  void spin() { ... }
  void rotateArms() { ... }
  void wiggleAntenas() { ... }

}

public class Sam implements 
  SpinRobot, 
  ArmsRobot { 
  
  Pair<Arm, Arm> arms;

  void sping() { ... }
  void rotateArms() { ... }
}

```

</div>
<div style="padding-top:20%;">

![](./images/isp.2.png)

</div>
</div>



---

![bg left](https://fakeimg.pl/800x600/246,120/?text=S)
![bg](https://fakeimg.pl/800x600/246,120/?text=O)
![bg](https://fakeimg.pl/800x600/246,120/?text=L)
![bg](https://fakeimg.pl/800x600/246,120/?text=I)
![bg](https://fakeimg.pl/800x600/246/fff/?text=D&font=lobster)


# Dependency <!-- 1fit -->
## Inversion <!-- fit -->
# Principle <!-- 1fit -->

---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=D)
![bg](https://fakeimg.pl/800x600/246/fff/?text=I)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)

# Princípio <!-- 1fit -->
# Inversão <!-- fit -->
# Dependência <!-- 1fit -->

---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=D)
![bg](https://fakeimg.pl/800x600/246/fff/?text=I)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)

<div class="cls">

<div >

![](./images/dip.1.png)

</div>

<div style="padding-top:20%">

``` java 

public class Robot {
  
  CutterArm arm = new CutterArm();

  // cortar 
  void cut(Pizza pizza) { 
    arm.cut(pizza);
  }
}

```

</div>
</div>


---

![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=D)
![bg](https://fakeimg.pl/800x600/246/fff/?text=I)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)

<div class="cls">

<div >

``` java 

public class Robot {
  
  ArmTool arm;
  
  // recebe a ferramenta 
  Robot(ArmTool arm) { 
    this.arm = arm;  
  }

  // cortar 
  void cut(Pizza pizza) { 
    arm.cut(pizza);
  }
}

```

</div>

<div>

![](./images/dip.2.png)


</div>
</div>

---


![bg left:20%](https://fakeimg.pl/800x600/246/fff/?text=D)
![bg](https://fakeimg.pl/800x600/246/fff/?text=I)
![bg](https://fakeimg.pl/800x600/246/fff/?text=P)

<div class="cls">

<div >

``` java 

Robot robot = new Robot(
  new ArmKnifeTool()
); 


Robot robot = new Robot(
  new ArmLaserTool()
); 

Robot robot = new Robot(
  new ArmPexeraTool()
); 


```

</div>

<div>

![](./images/dip.2.png)

</div>
</div>

---


![bg right:33%](https://fakeimg.pl/800x600/246/fff/?text=S)
![bg](https://fakeimg.pl/800x600/246/fff/?text=O)
![bg](https://fakeimg.pl/800x600/246/fff/?text=L)
![bg](https://fakeimg.pl/800x600/246/fff/?text=I)
![bg](https://fakeimg.pl/800x600/246/fff/?text=D)

# Isso é tudo pessoal! :+1: <!-- fit -->


Projeto: https://github.com/UeceComp-2022/solid

<br/>
<br/>
<br/>
<br/>

Responsáveis: 
  - Abraão Alves - https://github.com/AbraaoAlves
  - Kilvia Santos - https://github.com/KilviaSantos
  - Neydymar - https://github.com/NEYDYMAR48
