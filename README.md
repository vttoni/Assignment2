# Assignment2
makeCacheMatrix <- function(t = matrix()){
  inv <- NULL
  set <- function(f){
    t <<- f
    inv <<- NULL
  }
  get <- function() {t}
  setInverse <- function(inverse) {inv <<- inverse}
  getInverse <- function() {inv}
  list(set = set, get = get, setInverse = setInverse, getInverse = getInverse)
}
cacheSolve <- function(x, ...) {
  inv <- t$getInverse()
  if(!is.null(inv)){
    message("Getting cached data")
    return(inv)
  }
  mat <- t$get()
  inv <- solve(mat, ...)
  t$setInverse(inv)
}

![image](https://user-images.githubusercontent.com/87285373/125218711-5c742300-e278-11eb-94d7-a1bbb7ba79cb.png)
