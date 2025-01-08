% Data Table for Food Items
food_items = {
    'PEANUT BUTTER', 568.6, 20.3, 11.5, 130, 9.7, 27, 'C', '690225304789', 'Moderate Healthy';
    'BROWN RICE', 355, 0, 2.2, 8.6, 3.9, 11, 'A', '690225304788', 'Very Healthy';
    'CHOCOS', 373, 27.5, 1.2, 250, 7, 9, 'B', '8901499010742', 'Healthy';
    'MARIE GOLD BISCUIT', 445, 21.9, 5.2, 319, 0, 8.4, 'D', '8901063162426', 'Moderate Unhealthy';
    'MAGGI NOODLES', 384, 1.8, 8.2, 1028.3, 0, 8.2, 'E', '8901058000290', 'Very Unhealthy';
    'OATS', 407, 1.8, 1.9, 9.5, 10, 11.8, 'C', '8901491103800', 'Moderate Healthy';
    'DAIRY MILK CHOCOLATE', 530, 61.2, 16.9, 100, 0, 5.9, 'E', '7622201759711', 'Very Unhealthy';
    'LAYS (POTATO CHIPS)', 537, 3.4, 14.8, 643, 0, 6.7, 'E', '8901491101813', 'Very Unhealthy';
    'MILLET NOODLES', 358.1, 1.6, 0.3, 331.8, 0, 10.6, 'B', '8906131680598', 'Healthy';
    'CORN FLAKES', 378, 9.2, 0.6, 490, 0, 6.7, 'C', '8901499010216', 'Moderate Healthy';
};

% Prompt the user to enter a barcode
barcode_input = input('Enter Barcode Number: ', 's');

% Find the matching food item
match = false;
for i = 1:size(food_items, 1)
    if strcmp(food_items{i, 9}, barcode_input)
        match = true;
        fprintf('Food Item: %s\n', food_items{i, 1});
        fprintf('Energy (g): %.1f\n', food_items{i, 2});
        fprintf('Sugars (g): %.1f\n', food_items{i, 3});
        fprintf('Saturated Fatty Acids (g): %.1f\n', food_items{i, 4});
        fprintf('Sodium (mg): %.1f\n', food_items{i, 5});
        fprintf('Fiber (g): %.1f\n', food_items{i, 6});
        fprintf('Protein (g): %.1f\n', food_items{i, 7});
        fprintf('Nutri-Score: %s\n', food_items{i, 8});
        fprintf('Rating: %s\n', food_items{i, 10});
        break;
    end
end

if ~match
    fprintf('No matching food item found for the entered barcode.\n');
end

            
