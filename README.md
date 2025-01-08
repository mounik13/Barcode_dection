% Sample Data (Structured Array from the PDF)
data = struct( ...
    'barcode', { '8901491103800'}, ...
    'food_item', { 'OATS'}, ...
    'energy', [ 407], ...
    'sugars', [ 1.8], ...
    'saturated_fat', [ 1.9], ...
    'sodium', [ 9.5], ...
    'fiber', [ 10], ...
    'protein', [ 11.8], ...
    'nutri_score', { 'C'}, ...
    'rating', { 'Moderate Healthy'});

% Function to Fetch Product Details by Barcode
function product_details = fetch_details(barcode, data)
    % Initialize result
    product_details = [];
    
    % Search for barcode in data
    for i = 1:length(data)
        if strcmp(data(i).barcode, barcode)
            product_details = data(i);
            return;
        end
    end
    if isempty(product_details)
        disp('No product found for this barcode.');
    end
end

% Take User Input
barcode_input = input('Enter the barcode number: ', 's');

% Fetch Details
product_details = fetch_details(barcode_input, data);

% Display Results
if ~isempty(product_details)
    disp('Product Details:');
    disp(['Food Item: ', product_details.food_item]);
    disp(['Energy: ', num2str(product_details.energy), ' g']);
    disp(['Sugars: ', num2str(product_details.sugars), ' g']);
    disp(['Saturated Fat: ', num2str(product_details.saturated_fat), ' g']);
    disp(['Sodium: ', num2str(product_details.sodium), ' mg']);
    disp(['Fiber: ', num2str(product_details.fiber), ' g']);
    disp(['Protein: ', num2str(product_details.protein), ' g']);
    disp(['Nutri Score: ', product_details.nutri_score]);
    disp(['Rating: ', product_details.rating]);
end
