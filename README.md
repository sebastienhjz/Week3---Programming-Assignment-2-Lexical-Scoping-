# Week3---Programming-Assignment-2-Lexical-Scoping-

1.makeCacheMatrix

makeCacheMatrix<-function(x=matrix()){
        inv_x<-NULL
        set<-function(y){
        x<<-y
        inv_x<<-NULL
        }
        get<-function()x
        setinverse<-function(inverse)inv_x<<-inverse
        getinverse<-function()inv_x
        list(set=set,get=get,setinverse=setinverse,getinverse=getinverse)
}
        
cacheSolve<-function(x,...){
        inv_x<-x$getinverse()
        if(!is.null(inv_x)){
                  message("getting cached data")
                  return(inv_x)
        }
        data<-x$get()
        inv_x<-solve(data)
        x<-setinverse(inv_x)
        inv_x
}   
