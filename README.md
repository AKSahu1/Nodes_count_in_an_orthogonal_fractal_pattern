# Nodes_count_in_an_orthogonal_fractal_pattern
These MATLAB code would help us to count the number of different nodes of an orthogonal fractal fracture network, which can be used to calculate the connectivity of a fractal-fracture network.

img = imread('x6.bmp');
[nrow, ncol] = size(img);
nrow
ncol
I = 0;
X = 0;
Y = 0;
count = 0;
for i=2:nrow-1
    for j=2:ncol-1
        count = 0;
        if img(i,j)==0
          
            if img(i-1,j) == 0
            count = count + 1 ;
            end
            
            if img(i+1,j) == 0
            count = count + 1 ;
            end
            
            if img(i,j-1) == 0
            count = count + 1 ;
            end
            
            if img(i,j+1) == 0
            count = count + 1 ;
            end
            
            if count == 1
                   I = I + 1; 
            end
            
            if count == 3
                Y = Y + 1;
            end
            
            if count == 4
                 X = X + 1 ;
            end
            
        end
    end
    
end

left = sum(img(:,1) == 0)
bottom = sum(img(nrow,:) == 0)
top = sum(img(1,:) == 0)
right = sum(img(:,ncol) == 0)

I = I + left + bottom + top + right;

I
Y
X
