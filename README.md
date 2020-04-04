# utl_applying-format-for-groups-of-variables
Applying format for groups of variables
    Applying format for groups of variables

    github
    https://tinyurl.com/u5r9nck
    https://github.com/rogerjdeangelis/utl_applying-format-for-groups-of-variables


       Two solutions

            1, variable ranges
            2. macro utl_varlist

    macros
    https://tinyurl.com/y9nfugth
    https://github.com/rogerjdeangelis/utl-macros-used-in-many-of-rogerjdeangelis-repositories


    *_                   _
    (_)_ __  _ __  _   _| |_
    | | '_ \| '_ \| | | | __|
    | | | | | |_) | |_| | |_
    |_|_| |_| .__/ \__,_|\__|
            |_|
    ;
    data have;

    do id=1 to 10;

     monjan_dt   = int(200*uniform(1234) + 20000);
     monfeb_dt   = int(200*uniform(1234) + 20000);
     monmar_dt   = int(200*uniform(1234) + 20000);
     monapr_dt   = int(200*uniform(1234) + 20000);
     popjan      = int(10000*uniform(1234));
     popfeb      = int(10000*uniform(1234));
     popmar      = int(10000*uniform(1234));
     popapr      = int(10000*uniform(1234));
     dollarsjan  = int(30000*uniform(1234));
     dollarsfeb  = int(30000*uniform(1234));
     dollarsmar  = int(30000*uniform(1234));
     dollarsapr  = int(30000*uniform(1234));
     monmay_dt   = int(200*uniform(1234) + 20000);
     popmay      = int(10000*uniform(1234));
     dollarsmay  = int(10000*uniform(1234));

     output;

    end;
    run;quit;

    Up to 40 obs from HAVE total obs=10

          monjan_   monfeb_   monmar_   monapr_                                                                                           monmay_
     id      dt        dt        dt        dt     popjan   popfeb   popmar   popapr   dollarsjan   dollarsfeb   dollarsmar   dollarsapr      dt     popmay   dollar

      1    20048     20017     20076     20019    257581    88249    36299   107585     1337485       429374       117348      1368670     20017    905767     9674
      2    20147     20080     20074     20065    510277   283903   350611   255775     1309210       372007      2141788         8286     20102    905603     2344
      3    20159     20029     20023     20106    640857   772992   546362   977602     1604319      1263075      1479633      2830290     20141    347936     1810
      4    20175     20027     20063     20193    574431   314532   654413   546229     2079538      1807962       745727      1047216     20055    728259     9189
      5    20123     20142     20005     20140    337719   355450   520533   716976     1315693       486927      2489504      2198831     20030    523635     3813
      6    20182     20054     20118     20061    314132   295707   366100   561540     2957608       344887      2666520       182651     20009    788632     9217
      7    20171     20082     20001     20188    968923    63517   973705   864485      524860      2470977        21648      2463455     20021    749474     6344
      8    20191     20145     20032     20111    915597   294609   110804   872693     2184652      1669965      2408231      2724954     20171    161745     3892
      9    20089     20048     20073     20017    761006   609819     8095   534922      472774       745522      2364427      2103958     20192    607533     8821
     10    20089     20096     20193     20035    810604   544048    80665   658547     2212427      1285792      1973128      2586576     20012     85138     2065


    *            _               _
      ___  _   _| |_ _ __  _   _| |_
     / _ \| | | | __| '_ \| | | | __|
    | (_) | |_| | |_| |_) | |_| | |_
     \___/ \__,_|\__| .__/ \__,_|\__|
                    |_|
    ;

    Note the formats have been applied

    WANT total obs=10

                     Format as Date9                         comma12.                           Dollar15.                                 manual one by one
             -----------------------------------------   ------------------------------  --------------------------------------------   ---------------------------

    Obs  id  monjan_dt  monfeb_dt  monmar_dt  monapr_dt  popjan  popfeb  popmar  popapr  dollarsjan  dollarsfeb  dollarsmar  dollarsapr  monmay_dt  popmay  dollars

      1   1  21NOV2014  21OCT2014  19DEC2014  23OCT2014  2,575     882     362   1,075    $13,374      $4,293      $1,173     $13,686    21OCT2014  9,057     $9,67
      2   2  28FEB2015  23DEC2014  17DEC2014  08DEC2014  5,102   2,839   3,506   2,557    $13,092      $3,720     $21,417         $82    14JAN2015  9,056     $2,34
      3   3  12MAR2015  02NOV2014  27OCT2014  18JAN2015  6,408   7,729   5,463   9,776    $16,043     $12,630     $14,796     $28,302    22FEB2015  3,479     $1,81
      4   4  28MAR2015  31OCT2014  06DEC2014  15APR2015  5,744   3,145   6,544   5,462    $20,795     $18,079      $7,457     $10,472    28NOV2014  7,282     $9,18
      5   5  04FEB2015  23FEB2015  09OCT2014  21FEB2015  3,377   3,554   5,205   7,169    $13,156      $4,869     $24,895     $21,988    03NOV2014  5,236     $3,81
      6   6  04APR2015  27NOV2014  30JAN2015  04DEC2014  3,141   2,957   3,661   5,615    $29,576      $3,448     $26,665      $1,826    13OCT2014  7,886     $9,21
      7   7  24MAR2015  25DEC2014  05OCT2014  10APR2015  9,689     635   9,737   8,644     $5,248     $24,709        $216     $24,634    25OCT2014  7,494     $6,34
      8   8  13APR2015  26FEB2015  05NOV2014  23JAN2015  9,155   2,946   1,108   8,726    $21,846     $16,699     $24,082     $27,249    24MAR2015  1,617     $3,89
      9   9  01JAN2015  21NOV2014  16DEC2014  21OCT2014  7,610   6,098      80   5,349     $4,727      $7,455     $23,644     $21,039    14APR2015  6,075     $8,82
     10  10  01JAN2015  08JAN2015  15APR2015  08NOV2014  8,106   5,440     806   6,585    $22,124     $12,857     $19,731     $25,865    16OCT2014    851     $2,06

    *          _       _   _
     ___  ___ | |_   _| |_(_) ___  _ __  ___
    / __|/ _ \| | | | | __| |/ _ \| '_ \/ __|
    \__ \ (_) | | |_| | |_| | (_) | | | \__ \
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|___/
                     _       _     _
    __   ____ _ _ __(_) __ _| |__ | | ___   _ __ __ _ _ __   __ _  ___  ___
    \ \ / / _` | '__| |/ _` | '_ \| |/ _ \ | '__/ _` | '_ \ / _` |/ _ \/ __|
     \ V / (_| | |  | | (_| | |_) | |  __/ | | | (_| | | | | (_| |  __/\__ \
      \_/ \__,_|_|  |_|\__,_|_.__/|_|\___| |_|  \__,_|_| |_|\__, |\___||___/
    ;

    data want;
      set have;
             /* range of variables     manual  ranges */
      format monjan_dt  -- monapr_dt   monmay_dt     date9.;
      format popjan     -- popapr      popmay      comma12.;
      format dollarsjan -- dollarsapr  dollarsmay dollar15.;
    run;quit;

    proc print data=want width=min;
    run;quit;
    *                _ _     _
    __   ____ _ _ __| (_)___| |_
    \ \ / / _` | '__| | / __| __|
     \ V / (_| | |  | | \__ \ |_
      \_/ \__,_|_|  |_|_|___/\__|

    ;
    data want;
       set have;
       format %utl_varlist(have,prx=/_dt/i) date9.;
       format %utl_varlist(have,prx=/pop/i) comma12.;
       format %utl_varlist(have,prx=/dollars/i) dollar15.;
    run;quit;


