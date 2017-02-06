# Simulation-Girls-birth-number
# in this question, assume every family around the world will stop giving birth until they get their first girl, then what is the #probability of girls' number?
# below is a R funcion, simulate the probability according to input number of families n:

families=function(n){
  boys=0
  girls=0
  for(i in 1:n){
    genders=onefamily()
    girls=girls+genders[1]
    boys=boys+genders[2]
  }
  return(girls/(boys+girls))
}

onefamily=function(){
  boys=0
  girls=0
  while(girls==0){
    if(sample(c(TRUE,FALSE), 1)){
      girls=girls+1
    }else{
      boys=boys+1
    }
  }
  genders=c(girls,boys)
  return(genders)
}
